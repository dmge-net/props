# DMGE Props & NPC Library

The official open-source props and scripted actor library for the **Dungeon Master Game Engine (DMGE)**.

Includes static props, light-emitting fixtures, obstacle line-of-sight blockers, and autonomous NPCs scripted with waypoint patrols.

---

## 🎭 Prop Specification & Standards

Each prop definition in `manifest.json` conforms to the DMGE Prop Schema:

```json
{
  "id": "torch_wall",
  "name": "Wall Torch",
  "category": "lighting",
  "file": "lighting/torch_wall.svg",
  "width": 64,
  "height": 64,
  "castsShadow": false,
  "light": {
    "color": "#ff8822",
    "radius": 240,
    "intensity": 0.85,
    "flicker": true
  },
  "tags": ["light", "torch", "fire", "wall"]
}
```

### Scripted Actors & NPCs
Props can define autonomous patrol and reaction routines interpreted by DMGE's internal bytecode script runner:

```json
{
  "id": "skeleton_guard",
  "name": "Skeleton Sentinel",
  "category": "npcs",
  "file": "npcs/skeleton_guard.svg",
  "npc": {
    "movementType": "patrol",
    "facingMode": "topdown",
    "speed": 1.5,
    "script": "LABEL patrol_loop\nMOVE_TO 400 300 2\nWAIT 1.5\nMOVE_TO 600 300 2\nWAIT 1.5\nGOTO patrol_loop"
  }
}
```

---

## 📄 License

MIT License. Free to use in personal and commercial tabletop projects.
