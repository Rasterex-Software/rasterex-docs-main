---
title: Magnifier Object
sidebar_label: Magnifier Object
sidebar_position: 1
---

## Overview

The **Magnifier** is a viewer subsystem that provides high-precision visual inspection
and alignment capabilities. It is primarily used during interactive alignment workflows
where users need magnified, pixel-accurate feedback while positioning control points.

The Magnifier integrates tightly with:
- The viewer rendering pipeline
- Markup and annotation logic
- User interaction callbacks

---

## Responsibilities

The Magnifier object is responsible for:

- Rendering a magnified view of the underlying document content
- Synchronizing magnification with cursor or alignment points
- Managing overlay panels and visual guides
- Emitting callbacks during alignment workflows

---

## High-Level Architecture

At a high level, the Magnifier consists of:

- **Magnifier core object** – coordinates state and lifecycle
- **Magnify panel** – visual container responsible for rendering the zoomed view
- **Overlay logic** – guides, crosshairs, and alignment indicators
- **Callbacks & events** – integration points for host applications

