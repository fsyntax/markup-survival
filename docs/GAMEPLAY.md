# Markup Survival: Gameplay Mechanics

*Comprehensive guide to survival through code*

## Table of Contents
- [Core Survival Loop](#core-survival-loop)
- [Console Command System](#console-command-system)
- [Discovery-Based Learning](#discovery-based-learning)
- [Entity Growth & Progression](#entity-growth--progression)
- [Survival Mechanics](#survival-mechanics)
- [Environmental Systems](#environmental-systems)
- [Crafting & Resource Management](#crafting--resource-management)
- [Day/Night Survival Cycle](#daynight-survival-cycle)
- [Death & Failure States](#death--failure-states)
- [Advanced Discovery Techniques](#advanced-discovery-techniques)

## Core Survival Loop

### Life-or-Death Progression
Markup Survival is fundamentally about **staying alive** through coding skills. Every action must serve survival goals:

```
Spawn → Immediate Survival Needs → Resource Gathering → Tool Creation → Shelter Building → Advanced Survival → Death (or Success)
```

### Continuous Pressure
- **Health**: Decreases from damage, starvation, exposure
- **Hunger**: Constantly decreasing, death when critically low
- **Energy**: Required for all actions, depleted by activity
- **Warmth**: Critical during night and cold weather
- **Time**: Day/night cycle creates urgent timing requirements

### No Pause, No Safety
The game continues running even when you're thinking. Survival stats decrease in real-time, creating genuine pressure to act quickly and efficiently.

## Console Command System

### JavaScript-Only Interaction
All game interactions happen through JavaScript console commands. No clicking, no drag-and-drop—pure code.

```javascript
// Basic survival commands
inventory.apply('water', '.seed')           // Essential for plant growth
inventory.move('.torch', '#map .tile-x5-y3') // Place light sources strategically
inventory.combine('.stick', '.cloth')       // Discover crafting recipes
inventory.harvest('.tree.mature')           // Gather resources
player.moveTo(15, 20)                      // Navigate the world
world.inspect('.tile-x10-y5')              // Examine environment
```

### Command Discovery
- **help()**: Shows basic command categories
- **inventory.help()**: Lists inventory manipulation methods
- **player.help()**: Shows movement and action commands
- **world.help()**: Environment interaction commands

### Survival-Critical Commands
```javascript
// Emergency survival situations
player.eat('.fruit')                       // Consume food to prevent starvation
player.rest()                             // Restore energy (but costs time!)
inventory.light('.torch')                 // Create light source for visibility
player.seek_shelter()                     // Find protection from weather
```

### Error Feedback & Learning
Failed commands provide educational feedback:
```javascript
inventory.combine('.seed', '.stone')
// → "Seeds cannot be combined with stone. Try: water + seed for growth"

inventory.create('.tree')
// → "Cannot create trees directly. Must grow from seeds using water and time"

player.ignite('.wood')
// → "Fire requires ignition source. Try: torch + wood, or lightning + wood"
```

## Discovery-Based Learning

### Minimal Documentation Philosophy
The game intentionally provides minimal instructions. Players learn through:

1. **Logical Experimentation**: Real-world reasoning guides attempts
2. **Trial and Error**: Failed combinations teach what doesn't work
3. **Environmental Observation**: Watch natural patterns for clues
4. **Code Inspection**: Advanced players read source code for deep mechanics

### Discovery Progression

#### Beginner Discovery
```javascript
// Obvious combinations that make logical sense
inventory.apply('water', '.seed')     // → seed becomes wet, ready to grow
inventory.combine('.stick', '.cloth') // → torch (if ignition available)
inventory.harvest('.tree.mature')     // → wood resource
```

#### Intermediate Discovery
```javascript
// Requires understanding of prerequisites
inventory.combine('.wood', '.stone')  // → needs crafting surface
inventory.light('.wood')              // → needs existing fire source
inventory.build('.shelter')           // → needs multiple materials
```

#### Advanced Discovery
```javascript
// Found through code exploration and experimentation
inventory.ferment('.fruit', '.time')  // → preserved food
inventory.refine('.wood', '.fire')    // → charcoal
world.channel('.water', '.elevation') // → irrigation system
```

### Hint System (Minimal)
Instead of tutorials, the game provides subtle hints:
- **Environmental Clues**: Rain makes plants grow
- **Logical Patterns**: Fire spreads to flammable materials
- **Error Messages**: "Seeds need water to grow"
- **Visual Feedback**: Animations show cause and effect

## Entity Growth & Progression

### Natural Progression Rules
Entities follow realistic growth patterns that cannot be bypassed:

```html
<!-- Mandatory progression: cannot skip stages -->
<div class="seed">🌱</div>
<!-- + water + time → -->
<div class="seed wet growing">🌱</div>
<!-- + more time → -->
<div class="sapling">🌿</div>
<!-- + time + space → -->
<div class="tree young">🌳</div>
<!-- + time → -->
<div class="tree mature harvestable">🌳</div>
```

### Growth Requirements
Each stage has specific requirements discoverable through experimentation:

#### Seeds to Saplings
- **Water**: Must apply water to seeds
- **Time**: 30-60 seconds of game time
- **Space**: Cannot be overcrowded
- **Safety**: Protected from harsh weather

#### Saplings to Trees
- **Sunlight**: Day/night cycle affects growth
- **Space**: Adequate room for expansion
- **Time**: 60-120 seconds
- **Nutrients**: Proper soil conditions

#### Tree Maturity
- **Stability**: Protected from storms
- **Time**: Several minutes of growth
- **Health**: Not damaged by disease or pests

### Resource Constraints
- **Cannot Create Trees**: Must grow from seeds
- **Water Sources Required**: Cannot make things wet without water
- **Fire Needs Fuel**: Cannot create flames without combustible materials
- **Limited Starting Resources**: Forces strategic planning

## Survival Mechanics

### Critical Survival Stats

```javascript
const playerStats = {
  health: 100,      // Die at 0 - damaged by hazards, starvation
  hunger: 100,      // Decreases constantly - death when low
  energy: 100,      // Required for actions - rest to recover
  warmth: 50,       // Critical at night - fire/shelter needed
  visibility: 20    // Reduced in darkness - light sources help
}
```

### Death Conditions
- **Health = 0**: Immediate death from any cause
- **Hunger < 10**: Health decreases rapidly
- **Energy = 0**: Cannot perform survival actions
- **Warmth < 10** (at night): Health decreases from exposure

### Survival Priorities

#### Immediate (First 5 minutes)
1. **Plant seeds** - Food sources take time to grow
2. **Find/create water** - Essential for plant growth
3. **Gather basic materials** - Sticks, stones for tools

#### Short-term (First 30 minutes)
1. **Create fire** - Light and warmth for night survival
2. **Build basic shelter** - Protection from weather
3. **Establish food production** - Multiple food sources

#### Long-term (Ongoing)
1. **Tool advancement** - Better tools for better resources
2. **Shelter improvement** - Stronger protection
3. **Resource diversification** - Multiple survival strategies

### Failure States
- **Starvation**: No food sources established in time
- **Exposure**: No warmth sources for cold nights
- **Exhaustion**: Overexertion without rest
- **Environmental**: Storms, floods, other natural disasters

## Environmental Systems

### Day/Night Survival Cycle

#### Day (Safety Period)
```css
.world.day {
  visibility: 100%;
  temperature: warm;
  creature-spawning: safe;
  plant-growth: optimal;
}
```

- **Full Visibility**: Can see all entities and threats
- **Warmth**: No temperature threats
- **Safety**: Hostile creatures remain hidden
- **Growth**: Plants grow at normal rates

#### Night (Danger Period)
```css
.world.night {
  visibility: 20%;
  temperature: cold;
  creature-spawning: hostile;
  plant-growth: slowed;
}
```

- **Limited Visibility**: Only see nearby entities
- **Cold**: Warmth stat decreases without fire/shelter
- **Creatures**: Hostile entities spawn in darkness
- **Slowed Growth**: Plants grow slower or stop

### Weather as Survival Factor

#### Rain (Mixed Blessing)
```javascript
// Positive effects
plantGrowth.rate *= 2        // Plants grow faster
water.availability = true    // Natural water sources

// Negative effects
player.warmth -= 5          // Cold and wet
fire.extinguish = true      // Fires go out
visibility.reduction = 30%   // Harder to see
```

#### Storms (Major Threat)
```javascript
// Destruction
structures.damage = true     // Shelter takes damage
fires.extinguish = true     // All fires go out
visibility.reduction = 70%   // Severe visibility loss

// Opportunities
lightning.fire_chance = true // Can start fires
water.abundance = true      // Lots of water available
```

#### Drought (Resource Crisis)
```javascript
// Scarcity
water.availability = false  // No natural water
plant.growth_rate = 0.2     // Severely slowed growth
fire.spread_risk = true     // Fires spread faster
```

### Environmental Pressure
- **Resource Scarcity**: Limited materials force difficult choices
- **Time Pressure**: Weather changes create urgency
- **Location Strategy**: Safe vs resource-rich areas
- **Seasonal Planning**: Prepare for harsh seasons

## Crafting & Resource Management

### Discovery-Based Crafting
No recipe book—discover combinations through logical thinking:

```javascript
// Logical combinations (discoverable)
inventory.combine('.stick', '.cloth')  // → torch (needs fire)
inventory.combine('.wood', '.stone')   // → axe (needs tools)
inventory.combine('.fruit', '.time')   // → dried food

// Prerequisites required
inventory.combine('.seeds', '.soil')   // → needs planting location
inventory.combine('.metal', '.fire')   // → needs high temperature
```

### Resource Requirements

#### Water Sources
```javascript
// Cannot create water from nothing
world.find('.river')                   // Natural water source
inventory.collect_rainwater()          // During rain events
inventory.dig_well('.groundwater')     // Advanced technique
```

#### Fire Sources
```javascript
// Fire requires ignition + fuel
inventory.strike('.flint', '.steel')   // → spark
inventory.focus('.sunlight', '.lens')  // → concentrated heat
world.capture('.lightning')            // → natural ignition
```

#### Tool Progression
```javascript
// Hands → Basic Tools → Advanced Tools
inventory.gather('.stick')             // Hand gathering
inventory.craft('.knife', ['.stone'])  // Cut materials
inventory.forge('.axe', ['.metal'])    // Process raw materials
```

### Inventory Management
```javascript
// Limited inventory space forces decisions
inventory.capacity = 20                // Limited slots
inventory.drop('.item')               // Must discard items
inventory.prioritize('.survival')      // Essential items first

// Item degradation
tool.durability -= usage             // Tools break with use
food.spoilage += time                // Food rots over time
```

## Day/Night Survival Cycle

### Timing Your Survival
The day/night cycle creates urgent timing requirements:

#### Day Strategy (Preparation Time)
- **Gather Resources**: Safe time for exploration
- **Build/Repair**: Construct shelter and tools
- **Plant/Harvest**: Tend to food sources
- **Prepare for Night**: Stock fuel, food, materials

#### Night Strategy (Survival Mode)
- **Conserve Energy**: Minimal movement
- **Maintain Fire**: Critical for warmth and visibility
- **Stay in Shelter**: Protection from cold and creatures
- **Emergency Planning**: Prepare for unexpected threats

### Light Sources
```javascript
// Essential for night survival
inventory.light('.torch')             // Temporary light
inventory.build('.campfire')          // Area lighting
inventory.craft('.lantern')           // Portable light
world.reflect('.moonlight')           // Natural light (rare)
```

### Temperature Management
```javascript
// Prevent freezing at night
player.warmth.sources = [
  'fire',                            // Primary heat source
  'shelter',                         // Insulation
  'clothing',                        // Body heat retention
  'hot_food'                         // Internal warmth
]
```

## Death & Failure States

### How Players Die
Markup Survival features permanent death—mistakes have real consequences:

#### Starvation Death
```javascript
// Progression to death
hunger: 100 → 50 → 25 → 10 → 0
health: 100 → 90 → 70 → 40 → 0  // Death
```

#### Exposure Death
```javascript
// Cold night without warmth
warmth: 50 → 30 → 15 → 5 → 0
health: 100 → 80 → 50 → 20 → 0  // Death
```

#### Exhaustion Death
```javascript
// Overexertion without rest
energy: 100 → 20 → 5 → 0
action_capacity: limited → none    // Cannot act
health: slow_decline → death       // Unable to survive
```

### Learning from Failure
Death provides educational feedback:
- **Cause Analysis**: "Died from starvation - plant seeds earlier"
- **Timing Lessons**: "Died from cold - build fire before night"
- **Resource Lessons**: "Died from exhaustion - balance work and rest"

### Recovery Mechanics
- **No Saves**: Death means starting over completely
- **Knowledge Retention**: Players remember discovered recipes
- **Skill Transfer**: Coding skills improve with each playthrough

## Advanced Discovery Techniques

### Code Inspection for Deep Mechanics
Advanced players can explore the source code for hidden mechanics:

```javascript
// Discoverable in source code
const hiddenRecipes = {
  fermentation: { time: 600, temperature: 'warm' },
  metallurgy: { heat: 'extreme', tools: ['forge'] },
  chemistry: { catalyst: true, safety: 'required' }
}
```

### Environmental Easter Eggs
```javascript
// Hidden interactions discoverable through experimentation
inventory.experiment('.unknown', '.catalyst')
world.explore('.hidden_area')
time.wait_for('.special_event')
```

### Advanced Survival Strategies
```javascript
// Complex techniques for experienced players
automation.setup('.irrigation_system')
efficiency.optimize('.resource_pipeline')
resilience.build('.redundant_systems')
```

### Meta-Learning
- **Pattern Recognition**: Understanding game systems
- **Optimization**: Finding efficient survival strategies
- **Innovation**: Discovering new approaches through code
- **Teaching**: Sharing discoveries with other players

---

## Survival Philosophy

**Markup Survival** teaches web development through genuine survival pressure. Every command typed, every class applied, every function called serves the ultimate goal: **staying alive**.

The game succeeds when players find themselves thinking:
- "I need to write better code faster to survive"
- "Understanding this API could save my life"
- "Let me check the source code for better strategies"

*Survival is not guaranteed. Coding skills are essential. Discovery is everything.*
