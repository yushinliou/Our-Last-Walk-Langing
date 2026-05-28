---
title: "Designing the Bedroom"
description: "A look at the props we built in Blender for the game's landing room the turntable, the telephone, and the problems that came with them."
pubDate: 2026-05-29
author: "Dev. Apeel Subedi"
tags: ["blender", "3d", "art", "environment"]
---

*Our Last Walk* is set in multiple rooms, with bedroom as landing room. That made the room matter more than anything else — every prop needed to feel like it belonged to someone. And trust me the first impression is what makes people stick to the game longer.

Here's a quick look at the assets I built in Blender and the problems I ran into along the way, while finishing up the Bedroom.

## The Turntable

The master piece of the room. A vintage Pioneer-style record player with a full animation-ready hierarchy,  `Turntable_Root` holding a spinning `Platter` and a pivoting `Tonearm`. Materials were procedural: brushed aluminium on the body, a marble-veined plinth underneath.

The marble shader took a while to get right. Voronoi scale values that are too high produce a cracked-web pattern rather than bold, flowing veins. The fix was lower scale, stronger noise distortion, and a bit of patience.

Pivot alignment was another headache. Moving a parent empty after the mesh is built shifts everything unexpectedly. The safe pattern: snapshot all children's world matrices, move the parent, update the view layer, then restore each child's world position. In that order. Uff... It was a pain, but looking back now I feel proud of this product!

## The Telephone

A modern desk telephone, Bezier-curve handset with a banana profile, coiled NURBS cord hanging off the side, body with bevels, kickstand, label plates, and cradle rails.

The cord caused the most trouble. The taper object also needs to be explicitly linked to the scene collection even if it's hidden — otherwise it silently does nothing.

The hero angle is front-left three-quarter, so both the phone face and the hanging cord are visible at once.

Designing the telephone was more of an headache than writing an script for it in the unity.

## The Bedside Table

Simpler geometry, but the details matter in a room this small. Bevels on every edge, a warm wood material, clean proportions. Nothing interesting to report, which is exactly what you want from a bedside table.

## Getting Assets into Unity

Everything exports as FBX. The geometry and UVs come across cleanly. The materials do not.

Blender's Principled BSDF values — metallic, roughness, emission — don't transfer properly. Every material gets rebuilt by hand in Unity. One thing worth writing down: Blender's Roughness is Unity's Smoothness, inverted. A rough material in Blender is a smooth one in Unity unless you account for it.

## What's Left

The tonearm still needs its full animation — swing out over the record, cue-drop onto the platter. After that, the room is close to done.

One room. A lot of small things that add up. A good memory that'll last long with me!
