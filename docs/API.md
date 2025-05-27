# Markup Survival: Console API Reference

*Discovery-Based Command Interface*

This document provides a minimal reference for the JavaScript console commands in Markup Survival. Remember: **discovery through experimentation is encouraged over reading documentation.**

## Core Philosophy

- **Console-First**: All interactions happen through JavaScript commands
- **Discovery-Based**: Most commands and combinations are meant to be discovered
- **Survival-Focused**: Every command serves the goal of staying alive
- **Minimal Documentation**: Only essential survival hints provided

## Basic Survival Commands

### Player Actions
```javascript
// Essential survival commands
player.moveTo(x, y)           // Move to grid coordinates
player.eat(itemSelector)      // Consume food to prevent starvation
player.rest()                 // Restore energy (but time passes!)
player.status()               // Check health/hunger/energy

// Emergency commands
player.seek_shelter()         // Find nearest shelter automatically
player.call_for_help()        // Last resort survival tips
```

### Inventory Management
```javascript
// Basic inventory commands
inventory.list()              // Show current items
inventory.apply(item, target) // Apply item to target (discover effects)
inventory.move(item, location) // Place item at world location
inventory.drop(item)          // Remove item from inventory

// Discovery commands (experiment!)
inventory.combine(item1, item2) // Try crafting combinations
inventory.inspect(item)         // Learn about item properties
```

### World Interaction
```javascript
// Environment commands
world.inspect(location)       // Examine world tile
world.harvest(entitySelector) // Gather resources
world.plant(seedItem, location) // Plant seeds

// Discovery commands
world.find(entityType)        // Locate entities in world
world.weather()              // Check current conditions
```

## Help System

### Getting Started
```javascript
help()                       // Basic command categories
help.survival()             // Essential survival tips
help.console()              // Command syntax help
help.discover()             // Hints about experimentation
```

### Command-Specific Help
```javascript
inventory.help()            // Inventory command list
player.help()               // Player action commands  
world.help()                // World interaction commands
```

## Discovery Hints

### Logical Experimentation
Most commands and recipes follow real-world logic:
- Water + seed = growth
- Fire + wood = burning wood
- Stick + cloth = torch (if ignition available)

### Error Messages Teach
Failed commands provide educational feedback:
```javascript
inventory.create('tree')
// → "Cannot create trees directly. Grow from seeds using water and time."

inventory.combine('seed', 'stone')  
// → "Seeds don't combine with stone. Try: water + seed for growth."
```

## Survival Priority Commands

### Immediate Survival (First 5 Minutes)
```javascript
// Plant food sources immediately
inventory.apply('water', '.seed')
world.plant('.seed', {x: 5, y: 5})

// Gather basic materials
world.harvest('.stick')
world.harvest('.stone')
```

### Short-term Survival (First 30 Minutes)
```javascript
// Create fire for warmth and light
inventory.combine('.stick', '.cloth')  // Make torch
inventory.light('.torch')              // Create fire source

// Build basic shelter
inventory.combine('.wood', '.leaves')  // Try shelter materials
world.build('.shelter', {x: 10, y: 10})
```

## Entity Selectors

### Basic Selectors
```javascript
'.seed'          // All seeds
'.tree.mature'   // Mature trees only
'.water'         // Water sources
'.fire'          // Fire sources
'#player'        // The player
```

### Location Selectors  
```javascript
'#map .tile-x5-y3'      // Specific grid tile
'.tile[data-x="5"]'     // All tiles at X coordinate 5
'.player + .adjacent'   // Tiles next to player
```

## Advanced Discovery

### Experimentation Patterns
```javascript
// Try logical real-world combinations
inventory.combine('.metal', '.fire')   // Heating metal
inventory.combine('.fruit', '.time')   // Food preservation
inventory.combine('.water', '.fire')   // Steam/boiling

// Environmental interactions
world.expose('.item', '.rain')         // Weather effects
world.place('.item', '.sunlight')      // Solar exposure
```

### Code Inspection
Advanced players can explore the source code for deeper mechanics:
- Check `data/recipes.ts` for crafting combinations
- Examine `data/classes.ts` for CSS class effects
- Read `composables/useGameEngine.ts` for game mechanics

## Command Categories

### Survival Commands
- Player movement and actions
- Food and water consumption
- Shelter seeking and building
- Emergency survival functions

### Resource Commands  
- Harvesting materials from environment
- Inventory management and organization
- Item placement and world interaction
- Resource discovery and gathering

### Crafting Commands
- Experimental item combinations
- Crafting station interactions
- Tool creation and usage
- Advanced recipe discovery

### Discovery Commands
- World exploration and examination
- Item and entity inspection
- Help and hint systems
- Environmental observation

## Error Handling

### Common Errors
```javascript
// Resource constraints
inventory.combine('.wood', '.stone')
// → "Requires crafting surface. Build workbench first."

// Prerequisites missing
player.light('.campfire')  
// → "No ignition source available. Need torch or flint."

// Logical impossibilities
world.create('.tree')
// → "Trees must grow naturally from seeds. Use: seed + water + time"
```

### Discovery Through Failure
Errors guide learning:
- **Resource Requirements**: Learn what materials are needed
- **Prerequisites**: Understand required tools or conditions
- **Logical Constraints**: Real-world physics apply
- **Alternative Approaches**: Error messages suggest other methods

## Console Interface

### Command Syntax
- **Functions**: `player.eat('.fruit')` 
- **Selectors**: Use CSS-style selectors for targeting
- **Coordinates**: Grid positions as `{x: number, y: number}`
- **Chaining**: Some commands can be chained

### Autocomplete Support
The console provides intelligent suggestions:
- Available commands based on context
- Valid entity selectors for current world state
- Logical combination suggestions
- Error correction hints

## Survival Tips

### Critical Reminders
- **Time Never Stops**: Stats decrease while you think
- **Death is Permanent**: No saves or checkpoints
- **Discovery Rewards**: Experimentation teaches faster than documentation
- **Code Skills Save Lives**: Better programming = better survival

### Emergency Commands
```javascript
player.emergency()          // Show critical survival info
help.panic()               // Quick survival reminder
inventory.food()           // Find any edible items
world.safety()             // Locate nearest safe area
```

---

## Philosophy

The Markup Survival console API is designed to:
1. **Encourage Experimentation**: Try commands, see what happens
2. **Reward Logic**: Real-world reasoning guides successful attempts  
3. **Teach Through Failure**: Error messages provide educational value
4. **Minimize Hand-Holding**: Discovery over documentation

**Remember**: The best way to learn the API is to play the game. Start with basic survival needs and experiment your way to mastery.

*Your coding skills are your survival skills. The console is your lifeline.*
