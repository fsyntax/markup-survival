# Markup Survival Development Phases

*Solo Development Roadmap - Survival-Focused Discovery Game*

This document outlines a pragmatic development approach for building Markup Survival as a solo developer. Each phase focuses on core survival mechanics and discovery-based learning.

## Phase 1: Survival Foundation & Core Systems
**Priority**: Critical

### Project Setup & Survival Loop
- [ ] **Initialize Nuxt 3 project** with pnpm
  - [ ] Configure basic development environment
  - [ ] Set up project structure according to STRUCTURE.md
  - [ ] Create basic HTML layout with world grid
- [ ] **Implement Core Survival Engine**
  - [ ] Create GameEngine class with 60fps survival loop
  - [ ] Implement player stats (health, hunger, energy, warmth)
  - [ ] Add stat degradation system - player WILL die without action
  - [ ] Create basic game time management
- [ ] **Life-or-Death Mechanics**
  - [ ] Player death when health reaches 0
  - [ ] Hunger affects health when critically low
  - [ ] Energy depletion from actions

**Success Criteria**: Player dies from neglect, survival loop creates genuine urgency

### Basic Entity System & Natural Progression
- [ ] **Predefined Entity Classes**
  - [ ] Create comprehensive CSS class system (.wet, .burning, .fertile, etc.)
  - [ ] Implement logical class naming for intuitive discovery
  - [ ] Build class interaction rules (wet extinguishes burning, etc.)
- [ ] **Natural Growth System**
  - [ ] Seed → Sapling → Tree progression over time
  - [ ] Growth requirements: water, time, proper conditions
  - [ ] Cannot create trees directly - must grow from seeds
- [ ] **Basic World Grid**
  - [ ] Grid-based world system with tiles
  - [ ] Entity positioning and spatial relationships
  - [ ] Simple starting scenario with seeds and basic resources

**Success Criteria**: Seeds grow into trees naturally, cannot cheat by creating mature entities

### Console Interaction System
- [ ] **JavaScript Console Interface**
  - [ ] Basic console commands for entity interaction
  - [ ] inventory.apply(), inventory.move(), inventory.combine() functions
  - [ ] Command validation and error feedback
- [ ] **Resource Requirements**
  - [ ] Water sources required to make things wet
  - [ ] Cannot create resources from nothing
  - [ ] Realistic material constraints for all actions
- [ ] **Discovery Feedback**
  - [ ] Clear feedback for failed combinations
  - [ ] Hints about why actions don't work
  - [ ] Encouragement to experiment

**Success Criteria**: All interactions happen through console, logical resource requirements enforced

### Day/Night Survival Cycle
- [ ] **Day/Night Danger System**
  - [ ] Visual transition between day/night (affects visibility)
  - [ ] Reduced visibility at night creates survival pressure
  - [ ] Different threats/mechanics for day vs night
- [ ] **Environmental Survival Pressure**
  - [ ] Cold nights require warmth sources
  - [ ] Light sources become critical for visibility
  - [ ] Time pressure affects survival strategy

**Success Criteria**: Night time creates genuine survival challenges requiring preparation

---

## Phase 2: Discovery & Crafting Systems
**Priority**: Critical

### Resource Discovery & Harvesting
- [ ] **Harvestable Resources**
  - [ ] Mature trees provide wood when harvested
  - [ ] Stone gathering from rock formations
  - [ ] Basic resource types with realistic sources
- [ ] **Tool Requirements**
  - [ ] Progressive tool needs for different resources
  - [ ] Cannot harvest everything with bare hands
  - [ ] Tool durability and degradation system
- [ ] **Resource Scarcity**
  - [ ] Limited starting materials force strategic choices
  - [ ] Resources don't regenerate instantly
  - [ ] Survival pressure drives resource management

**Success Criteria**: Resource gathering feels realistic and requires planning

### Inventory & Item Management
- [ ] **Console-Based Inventory**
  - [ ] Inventory manipulation through JavaScript commands
  - [ ] Item properties and data attributes
  - [ ] Stack limits and inventory constraints
- [ ] **Item Persistence**
  - [ ] Items maintain state between actions
  - [ ] Durability tracking for tools and equipment
  - [ ] Food spoilage and item degradation over time
- [ ] **Inventory Commands**
  - [ ] Move items between inventory and world
  - [ ] Inspect item properties and states
  - [ ] Organize and manage limited inventory space

**Success Criteria**: Inventory management through console feels intuitive but requires skill

### Discovery-Based Crafting
- [ ] **Experimental Crafting System**
  - [ ] No recipe book - discovery through experimentation
  - [ ] Logical combinations that make real-world sense
  - [ ] Clear feedback for failed attempts
- [ ] **Core Survival Recipes**
  - [ ] Stick + Cloth → Torch (if fire source available)
  - [ ] Wood + Stone → Basic Tools (if crafting surface available)
  - [ ] Prerequisites and crafting station requirements
- [ ] **Recipe Discovery**
  - [ ] Trial and error reveals working combinations
  - [ ] Environmental clues guide logical attempts
  - [ ] Advanced recipes discoverable through code inspection

**Success Criteria**: Players discover recipes through logical thinking, not documentation

### Shelter & Defense Systems
- [ ] **Shelter Building**
  - [ ] Protection from weather and environmental threats
  - [ ] Material requirements for different shelter types
  - [ ] Shelter durability and maintenance needs
- [ ] **Environmental Threats**
  - [ ] Weather systems that require shelter
  - [ ] Temperature management for survival
  - [ ] Environmental hazards that damage player/structures
- [ ] **Basic Defense**
  - [ ] Light sources ward off nighttime dangers
  - [ ] Fire provides warmth and protection
  - [ ] Defensive structures using discovered materials

**Success Criteria**: Shelter becomes necessary for survival, not optional convenience

---

## Phase 3: Environmental Pressure & Discovery
**Priority**: Important

### Weather & Seasonal Survival
- [ ] **Weather as Survival Factor**
  - [ ] Rain essential for plant growth but causes exposure
  - [ ] Storms damage structures and extinguish fires
  - [ ] Drought makes water sources critical
- [ ] **Seasonal Challenges**
  - [ ] Different survival requirements per season
  - [ ] Resource availability changes with seasons
  - [ ] Preparation required for harsh seasons
- [ ] **Environmental Discovery**
  - [ ] Weather patterns affect class interactions
  - [ ] Environmental clues guide survival strategies
  - [ ] Natural cycles create rhythm and urgency

**Success Criteria**: Weather creates meaningful survival challenges requiring adaptation

### Advanced Discovery Systems
- [ ] **Complex Class Interactions**
  - [ ] Multi-step transformations through class combinations
  - [ ] Chemical-like reactions between elements
  - [ ] Chain reactions and cascade effects
- [ ] **Advanced Crafting**
  - [ ] Multi-stage crafting processes
  - [ ] Tool requirements for advanced items
  - [ ] Specialized crafting stations and environments
- [ ] **Deep Mechanics Discovery**
  - [ ] Hidden mechanics discoverable through code inspection
  - [ ] Advanced strategies requiring experimentation
  - [ ] Easter eggs and secret combinations

**Success Criteria**: Advanced players find depth through code exploration

### Hostile Environment & Threats
- [ ] **Survival Threats**
  - [ ] Environmental hazards that spawn based on conditions
  - [ ] Threats that require specific defenses or strategies
  - [ ] Escalating difficulty as time progresses
- [ ] **Resource Competition**
  - [ ] Scarcity mechanics that force difficult choices
  - [ ] Risk/reward decisions for resource gathering
  - [ ] Time pressure for critical survival actions
- [ ] **Emergency Survival**
  - [ ] Crisis situations requiring quick thinking
  - [ ] Emergency console commands for desperate situations
  - [ ] Recovery from near-death experiences

**Success Criteria**: Game consistently challenges player survival skills

---

## Phase 4: Polish & Launch Preparation
**Priority**: Important

### Survival Balance & Testing
- [ ] **Difficulty Tuning**
  - [ ] Balance survival pressure without frustration
  - [ ] Adjust resource scarcity and discovery difficulty
  - [ ] Fine-tune progression and learning curve
- [ ] **Discovery Optimization**
  - [ ] Ensure logical combinations are discoverable
  - [ ] Improve feedback for failed experiments
  - [ ] Balance hints vs. discovery challenge
- [ ] **Edge Case Handling**
  - [ ] Fix survival exploits and unintended shortcuts
  - [ ] Handle error states gracefully
  - [ ] Ensure consistent survival pressure

**Success Criteria**: Game feels challenging but fair, discovery feels rewarding

### Documentation & Launch
- [ ] **Minimal Player Documentation**
  - [ ] Basic survival hints only
  - [ ] Console command reference
  - [ ] Encouragement to explore and experiment
- [ ] **Developer Documentation**
  - [ ] Code structure documentation for future development
  - [ ] System architecture overview
  - [ ] Extension points for future features
- [ ] **Launch Preparation**
  - [ ] Set up deployment pipeline
  - [ ] Create demo/trailer showcasing survival gameplay
  - [ ] Prepare for solo launch and feedback collection

**Success Criteria**: Game is publicly available with minimal but sufficient documentation

---

## Success Metrics

### MVP Success (End of Phase 2)
- [ ] Player dies consistently without skillful survival actions
- [ ] Discovery system rewards experimentation and logical thinking
- [ ] Console interface feels natural for JavaScript developers
- [ ] Resource management creates meaningful strategic decisions
- [ ] Day/night cycle creates genuine survival pressure

### Discovery Success (End of Phase 3)
- [ ] Players discover crafting recipes through experimentation
- [ ] Environmental systems create dynamic survival challenges
- [ ] Advanced mechanics reward code exploration
- [ ] Failure teaches rather than frustrates

### Launch Success (End of Phase 4)
- [ ] Zero critical bugs in core survival systems
- [ ] Discovery system feels rewarding rather than opaque
- [ ] Game teaches web development through survival necessity
- [ ] Documentation encourages experimentation over hand-holding

---

## Risk Mitigation

### Development Risks
- **Scope Creep**: Focus on survival core, save exploration modes for later
- **Discovery Balance**: Regular playtesting to ensure discoverability
- **Solo Burnout**: Maintain sustainable pace, celebrate small wins

### Design Risks
- **Too Difficult**: Balance survival pressure with learning opportunity
- **Too Easy**: Ensure genuine survival challenge throughout
- **Poor Discovery**: Test that logical combinations are findable

### Technical Risks
- **Console Complexity**: Keep command interface simple but powerful
- **Browser Compatibility**: Focus on modern browsers for MVP
- **Save System**: Implement basic persistence early to prevent frustration


---

*This roadmap prioritizes survival mechanics and discovery over convenience features. The goal is creating a game where coding skills are essential for survival, not just helpful for exploration.*
