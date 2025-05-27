# 🔥 Markup Survival: Code to Live, Style to Survive

## Table of Contents
- [Overview](#overview)
- [Core Concept](#core-concept)
- [Game Logic Architecture](#game-logic-architecture)
- [World Representation](#world-representation)
- [Survival Mechanics](#survival-mechanics)
- [Gameplay Flow](#gameplay-flow)
- [Console Interaction System](#console-interaction-system)
- [Environmental Systems](#environmental-systems)
- [Entity Progression System](#entity-progression-system)
- [Inventory & Crafting Discovery](#inventory--crafting-discovery)
- [Learning Integration](#learning-integration)
- [Technical Implementation](#technical-implementation)
- [Solo Development Approach](#solo-development-approach)
- [MVP Scope](#mvp-scope)

## Overview

**Markup Survival** is a unique browser-based survival game where the DOM is the game world and **survival is the primary goal**. Players must code their way to survival by writing HTML, discovering CSS class combinations, and using JavaScript console commands to manipulate their environment in real-time.

**Target Audience**: Web developers and coding students who want to learn through high-stakes survival gameplay.

**Core Philosophy**: Discovery through experimentation. Documentation is minimal by design—players learn by trying, failing, and exploring the codebase itself.

## Core Concept

### The DOM as Reality
- **No Canvas/WebGL**: The entire game world exists as manipulatable DOM elements
- **HTML Elements = Game Entities**: `<div class="tree">`, `<span class="stone">`, `<article class="shelter">`
- **Predefined CSS Classes = Entity States**: `.burning`, `.wet`, `.glowing`, `.fertile`, `.dangerous`
- **JavaScript Console = Player Interface**: Direct DOM manipulation through code commands

### Survival Through Code
Players don't click buttons to survive—they write code to avoid death:
```html
<!-- Start with a seed (can't create trees directly) -->
<div class="seed">🌱</div>

<!-- Find/apply water to help it grow -->
<!-- inventory.apply('water', '.seed') -->
<div class="seed wet">🌱</div>

<!-- Natural progression: seed → sapling → tree -->
<div class="sapling">🌿</div>
<div class="tree">🌳</div>
```

### Discovery-Based Learning
- **Minimal Documentation**: Only basic survival hints provided
- **Logical Class Names**: CSS classes follow intuitive naming for discovery
- **Experimentation Encouraged**: Trial and error reveals crafting recipes
- **Code Exploration**: Players dig into source code for deeper understanding

## Game Logic Architecture

### Core Game Loop (60fps)
1. **Survival Pressure**: Health, hunger, energy decrease continuously
2. **Time Progression**: Day/night cycle affects visibility and threats
3. **State Updates**: All entities check conditions and update naturally
4. **Threat Management**: Environmental hazards and creatures spawn
5. **Player Actions**: Console commands and code changes processed

### Entity State Management
```javascript
// Example entity structure (discoverable in code)
const entity = {
  id: 'tree_001',
  type: 'tree',
  element: HTMLElement,
  properties: {
    health: 100,
    growth: 75,
    moisture: 50,
    harvestable: true
  },
  classes: ['tree', 'mature', 'wet'],
  location: { x: 10, y: 15 }
}
```

### Predefined Class System
- **Game-Defined Classes**: All functional classes are built into the system
- **Logical Naming**: `.wet`, `.burning`, `.frozen`, `.fertile`, `.rotten`
- **Discoverable Interactions**: Players experiment to find class effects
- **No User CSS**: Players cannot define new classes, only use existing ones

## World Representation

### Spatial Grid System
```html
<div id="world" class="grid-20x20">
  <div class="tile" data-x="0" data-y="0"></div>
  <div class="tile" data-x="1" data-y="0"></div>
  <!-- ... -->
</div>
```

### Entity Hierarchy & Natural Progression
- **Seeds**: Must be grown, cannot create trees directly
- **Saplings**: Intermediate growth stage from seeds
- **Trees**: Mature stage, harvestable for resources
- **Items**: Require proper sources (water from rivers, not thin air)
- **Structures**: Built from gathered materials, not created arbitrarily

### Realistic Resource Requirements
- **Water Sources**: Must find/create water to make things `.wet`
- **Fire Sources**: Need fuel and ignition to create `.burning` items
- **Material Constraints**: Can't create resources without proper sources

## Survival Mechanics

### Life-or-Death Stats
```javascript
const player = {
  health: 100,    // Die at 0
  hunger: 100,    // Affects health when low
  energy: 100,    // Required for actions
  warmth: 50,     // Critical in cold/night
  visibility: 20  // Reduced in darkness
}
```

### Immediate Threats
1. **Starvation**: Hunger decreases constantly, death is inevitable without food
2. **Exposure**: Cold nights and weather require shelter/fire
3. **Exhaustion**: Actions consume energy, rest required
4. **Darkness**: Limited visibility spawns dangers
5. **Hostile Creatures**: Spawn under specific threatening conditions

### Survival Priority
- **Food Chain**: Seeds → plants → food → survival
- **Shelter Building**: Protection from elements and creatures
- **Tool Crafting**: Better tools = better survival chances
- **Resource Management**: Limited resources require strategic planning

## Gameplay Flow

### Starting State (Minimal Resources)
```html
<!-- Player starts in survival situation -->
<div id="world">
  <div class="player" data-health="100" data-hunger="75">🧑‍💻</div>
  <div class="seed">🌱</div>
  <div class="seed">🌱</div>
  <div class="stone">🪨</div>
</div>
```

### Survival Actions Through Console
1. **Resource Gathering**: `inventory.harvest('.tree.mature')`
2. **Item Movement**: `inventory.move('.torch', '#map .tile-x5-y3')`
3. **Crafting Attempts**: `inventory.combine('.stick', '.cloth')`
4. **Shelter Building**: `inventory.place('.shelter', '#map .tile-x10-y10')`
5. **Emergency Actions**: Quick commands for immediate threats

### Discovery Mechanics
- **Trial and Error**: Try combining items to find recipes
- **Environmental Clues**: Observe natural patterns for hints
- **Code Inspection**: Advanced players can read source for deeper mechanics
- **Logical Deduction**: Class names and behaviors follow real-world logic

## Console Interaction System

### JavaScript Command Interface
```javascript
// Example console commands (subject to development)
inventory.apply('water', '.seed')              // Add water to seeds
inventory.move('.torch', '#map .tile-x42-y77') // Place torch at location
inventory.combine('.stick', '.cloth')          // Attempt crafting
inventory.harvest('.tree.mature')              // Gather resources
player.moveTo(42, 77)                         // Move player
world.inspect('.tile-x5-y5')                  // Examine location
```

### Command Discovery
- **Help System**: Basic command list available
- **Autocomplete**: Console suggests available methods
- **Error Feedback**: Clear messages for invalid operations
- **Progressive Unlock**: Advanced commands discovered through play

### No Drag-and-Drop
- **Console-Only**: All interactions through JavaScript commands
- **Intentional Friction**: Coding required for every action
- **Educational Focus**: Reinforces programming concepts constantly

## Environmental Systems

### Day/Night Survival Cycle
```css
/* Day: Safety and visibility */
.world.day { visibility: 100%; }
.world.day .creature.hostile { display: none; }

/* Night: Danger and limited vision */
.world.night { filter: brightness(0.3); }
.world.night .creature.hostile { display: block; }
.world.night .player:not(.near-light) { visibility: 20%; }
```

### Weather as Survival Factor
- **Rain**: Essential for plant growth, but causes exposure
- **Storms**: Destroy structures, extinguish fires, create danger
- **Drought**: Plants die without manual watering
- **Seasons**: Affect resource availability and survival difficulty

### Environmental Pressure
- **Resource Scarcity**: Limited materials force difficult choices
- **Time Pressure**: Stats decrease continuously, no pause
- **Location Matters**: Safe vs dangerous areas affect survival

## Entity Progression System

### Natural Growth Requirements
```javascript
// Growth requires proper conditions (discoverable)
const growthRules = {
  seed: {
    requirements: ['wet', 'time'],
    becomes: 'sapling',
    duration: 30000 // 30 seconds
  },
  sapling: {
    requirements: ['sunlight', 'space', 'time'],
    becomes: 'tree',
    duration: 60000 // 60 seconds
  },
  tree: {
    requirements: ['mature'],
    harvestable: true,
    resources: ['wood', 'fruit']
  }
}
```

### Realistic Constraints
- **Cannot Create Trees**: Must grow from seeds
- **Water Sources Required**: Cannot make things wet without water
- **Fire Needs Fuel**: Cannot create burning items without combustible materials
- **Tool Requirements**: Better tools needed for advanced resources

### Decay and Maintenance
- **Food Spoilage**: Items rot over time without preservation
- **Tool Degradation**: Equipment breaks with use
- **Structure Damage**: Buildings require maintenance
- **Plant Death**: Neglected plants wither and die

## Inventory & Crafting Discovery

### Inventory as Code Objects
```html
<div id="inventory">
  <div class="item wood" data-quantity="5" data-durability="100">🪵</div>
  <div class="item stone" data-quantity="3">🪨</div>
  <div class="item torch" data-fuel="80" data-light-radius="3">🔦</div>
</div>
```

### Crafting Through Experimentation
```javascript
// Players discover recipes through trial and error
// No recipe book provided - must experiment!

// Example discovered through logical thinking:
inventory.combine('.stick', '.cloth')  // → torch (if fire available)
inventory.combine('.wood', '.stone')   // → axe (if crafting station available)
inventory.combine('.seed', '.water')   // → wet seed (ready to plant)
```

### Discovery Progression
- **Logical Combinations**: Real-world reasoning guides experimentation
- **Failure Feedback**: Clear messages about why combinations don't work
- **Prerequisites**: Some recipes require tools or stations
- **Advanced Techniques**: Complex recipes found through code exploration

## Learning Integration

### Educational Philosophy
1. **Discovery Over Documentation**: Learn by doing, not reading
2. **Real Consequences**: Mistakes have survival costs
3. **Progressive Complexity**: Start simple, complexity emerges naturally
4. **Code-First Thinking**: Every action reinforces programming concepts

### Skills Developed
- **DOM Manipulation**: Direct element control through console
- **CSS Class Logic**: Understanding state through class systems
- **JavaScript Proficiency**: Console commands require proper syntax
- **Problem-Solving**: Survival pressure encourages creative solutions
- **Code Reading**: Advanced strategies require source code exploration

### Professional Relevance
- **Debugging Skills**: Inspecting elements and understanding state
- **API Interaction**: Console commands mirror API usage patterns
- **State Management**: Entity properties reflect application state patterns
- **Resource Management**: Mirrors performance and memory concerns

## Technical Implementation

### Architecture Overview (Solo Development)
```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Game Engine   │◄──►│   DOM Manager   │◄──►│ Console System  │
│                 │    │                 │    │                 │
│ • Survival Loop │    │ • Entity CRUD   │    │ • Command Parse │
│ • Threat System │    │ • Class Mgmt    │    │ • API Interface │
│ • Time/Weather  │    │ • Discovery     │    │ • Autocomplete  │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Technology Stack
- **Frontend Framework**: Nuxt 3 (confirmed)
- **Package Manager**: pnpm
- **Other Technologies**: TBD during development

### Development Priorities
1. **Survival Core**: Life-threatening mechanics first
2. **Discovery System**: Class interactions and crafting
3. **Console Interface**: JavaScript command system
4. **Environmental Pressure**: Weather, time, threats

## Solo Development Approach

### Development Philosophy
- **100% Solo Project**: No external contributions during initial development
- **Iterative Discovery**: Build systems, then discover through play
- **Minimal Documentation**: Let the code teach itself
- **Survival-First**: Every feature must serve survival gameplay

### MVP Development Order
1. **Survival Stats**: Health/hunger/energy decreasing over time
2. **Basic Entities**: Seeds, saplings, trees with growth progression
3. **Console Commands**: Basic inventory manipulation
4. **Resource Requirements**: Water sources, fire creation, etc.
5. **Day/Night Cycle**: Visibility and threat changes
6. **One Crafting Chain**: Stick + cloth = torch (with prerequisites)

### Future Expansion
- **Creative Mode**: Sandbox for learning without survival pressure
- **Advanced Mechanics**: Complex chemistry through class combinations
- **Community Features**: Player-shared discoveries and strategies
- **Educational Tools**: Structured lessons using survival scenarios

## MVP Scope

### Critical Survival Features
- [ ] **Life-Threatening Stats**: Constantly decreasing survival metrics
- [ ] **Natural Growth**: Seed → sapling → tree progression system
- [ ] **Console Interface**: JavaScript commands for all interactions
- [ ] **Resource Constraints**: Realistic material requirements
- [ ] **Day/Night Danger**: Visibility and threat changes
- [ ] **Discovery Crafting**: Experimental recipe system

### Enhanced Survival Features
- [ ] **Weather Threats**: Environmental hazards affecting survival
- [ ] **Hostile Creatures**: Spawning dangers requiring defense
- [ ] **Tool Requirements**: Progressive tool needs for resources
- [ ] **Shelter Building**: Protection from elements

### Quality of Life Features
- [ ] **Command Autocomplete**: Console assistance
- [ ] **State Inspection**: Debugging tools for game state
- [ ] **Save/Load**: Survival progress persistence
- [ ] **Hint System**: Minimal survival tips

---

*This concept document emphasizes survival, discovery, and learning through experimentation. The goal is creating genuine survival pressure that drives learning through necessity, not curiosity alone.*
