---
title: Text Markup Editing Model
sidebar_label: Text Editing Model
---

## Overview

Text-based markups in the Rasterex Web SDK (such as **Text Box** and **Callout**) are composed of two distinct parts:

1. **Markup geometry**, created and managed by RxCore
2. **Text content**, edited and managed by the host application UI

In short: RxCore is responsible for creating, rendering, and persisting the markup geometry.  
The host application is responsible for providing a user interface for text entry and editing.

This document describes the recommended **editing lifecycle and interaction model** for text-based markups.

---

## Applicable Markup Types

This model applies to the following markup creation methods:

- Text Box (`markup.create.text`)
- Callout (`markup.create.callout`)

Both behave identically with respect to text editing. The only difference is that callouts include an additional leader/arrow geometry.

---

:::info Required Callback
Handling the `GUI_TextInput` callback is required to support Text Box and
Callout markups. Without it, text input and editing will not function.
:::

- [GUI_TextInput Callback](./callbacks/GUI_TextInput)



## Components

### Markup Geometry (RxCore)

- Created via interactive tools:
  - `RxCore.markUpTextRect(true)`
  - `RxCore.markUpTextRectArrow(true)`
- Geometry includes:
  - position (`x`, `y`)
  - size (`w`, `h`)
  - style properties
- Creation is reported via the `GUI_Markup` callback with `operation.created === true`

RxCore does **not** provide a built-in text editor.

---

### Text Editor Overlay (Host UI)

The host application must provide a text editing UI, typically implemented as:

- An HTML overlay (`contenteditable`, input field, or textarea)
- Absolutely positioned over the markup bounds
- Shown only while editing

This approach allows:
- native text input behavior
- copy/paste and IME support
- accessibility and styling flexibility

---

---

## GUI_TextInput Callback

Text input for text-based markups is coordinated through the
`GUI_TextInput` connection callback.

This callback is invoked by RxCore whenever text editing is required for a
Text Box or Callout markup and provides the information needed to bind an
external HTML editor to the markup.

### Purpose

`GUI_TextInput` acts as the integration point between:

- RxCore-managed markup geometry, and
- the host-provided text editing UI.

RxCore does not render or manage text input directly. Instead, it notifies
the host application when text input should begin, update, or be committed.

---

### Callback Responsibilities

When `GUI_TextInput` is triggered, the host application SHOULD:

- Position the text editor using the provided rectangle (`textrect`)
- Populate the editor with the current markup text (`getText()`)
- Enable editing when `operation.edit === true`
- Commit text changes using `setText(text)` when editing completes

---

### Callback Parameters

The callback provides:

- **`textrect`**  
  A rectangle describing the position and size of the text markup.  
  This should be used to position and size the editor overlay.

- **`operation`**  
  An object describing the current editing state:

  ```js
  operation = {
    start: false,
    create: false,
    edit: false,
    save: false
  }


## Editing Lifecycle

### 1. Placement Mode

- The host enables the text or callout tool.
- The user places the markup geometry on the page.

### 2. Creation

- RxCore emits a `GUI_Markup` event with `operation.created === true`.
- The host records the created markup reference and its bounds.

### 3. Editor Activation

The host opens the text editor when:
- a new text or callout markup is created (recommended), or
- an existing text or callout markup is selected

The editor:
- is positioned at the markup’s `x` / `y`
- is sized using `w` / `h`
- is populated with existing text (if any)
- receives input focus immediately

---

### 4. Live Editing

- User edits text in the overlay UI.
- Host may:
  - update the markup text live, or
  - defer updates until commit

Live updates are optional but useful for previews or collaboration.

---

### 5. Commit

- The editor is committed when it loses focus (`blur`), or via an explicit save action.
- The host writes the final text value back to the markup object.
- The editor overlay is hidden.

This “commit on blur” behavior is the recommended default for simple integrations.

---

### 6. Cancel (Optional)

Hosts may optionally support cancellation (for example via `Esc`):

- revert text to its previous value, or
- delete the newly created markup if no text was committed

Cancel semantics are host-defined and not enforced by RxCore.

---

## Normative Integration Notes

- RxCore **creates geometry only** for text-based markups.
- The host application **MUST provide** a text editing UI.
- The editor overlay **MUST track markup bounds** to maintain visual alignment.
- Text editing behavior is independent of markup creation and styling.
- This model applies uniformly to both Text Box and Callout markups.

---

## Related Topics

- Markup Creation Methods
- Markup Style Defaults and Scope
- `GUI_Markup` Callback Events
- User Identity and Annotation Attribution
