# 🔥 Markup Survival: Code to Live, Style to Survive

*A unique browser-based survival game where the DOM is your world and code is your tool for survival.*

[![Nuxt](https://img.shields.io/badge/Nuxt-002E3B?logo=nuxtdotjs&logoColor=#00DC82)](https://nuxt.com/)

## 🎮 What is Markup Survival?

Markup Survival is an innovative educational game that combines web development learning with survival gameplay. Instead of clicking buttons or using a traditional UI, players survive by writing HTML, applying CSS classes, and using JavaScript to manipulate their environment in real-time.

**Key Features:**
- **The DOM is the World**: Every game entity exists as an HTML element
- **Predefined CSS Classes**: Discover logical class combinations through experimentation
- **JavaScript Console Interface**: Interact with the world through code commands
- **Educational Focus**: Learn web development through engaging survival gameplay
- **Real-time Feedback**: Code changes reflect immediately in the game world

## 🚀 Quick Start

### Prerequisites
- Node.js (v18.0.0 or higher)
- pnpm package manager
- Modern web browser (Chrome, Firefox, Safari, Edge)

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/markup-survival.git
cd markup-survival

# Install dependencies
pnpm install

# Start development server
pnpm run dev
```

The game will be available at `http://localhost:3000`

### First Steps in Game

1. **Plant a Seed**: Begin your survival journey
   ```html
   <div class="seed">🌱</div>
   ```

2. **Find Water**: Seeds need water to grow
   ```javascript
   // Use the console to add water
   inventory.apply('water', '.seed')
   ```

3. **Survive**: Your hunger, health, and energy decrease over time
4. **Discover**: Experiment with class combinations to find crafting recipes

## 📚 Documentation

### Core Documentation
- **[📖 CONCEPT.md](docs/CONCEPT.md)** - Complete game design and vision
- **[🗓️ PHASES.md](docs/PHASES.md)** - Development roadmap and milestones
- **[📁 STRUCTURE.md](docs/STRUCTURE.md)** - Project organization and architecture
- **[🎮 GAMEPLAY.md](docs/GAMEPLAY.md)** - Detailed gameplay mechanics
- **[🔧 API.md](docs/API.md)** - Internal systems and API reference

### Survival Hints
> **💡 Discovery is key!** Most crafting recipes and mechanics are meant to be discovered through experimentation. Check the source code for deeper insights when needed.

- Start with basic seeds and water
- Growth follows logical progression: seed → sapling → tree
- Fire provides warmth and light
- Explore class combinations for crafting

## 🎯 Game Concept

In Markup Survival, you don't just play a game—you code your survival. The game world exists entirely as DOM elements, and every interaction happens through code. Your primary goal is **survival** through strategic coding and resource management.

```html
<!-- Growth progression example -->
<div class="seed wet">🌱</div>
<!-- Time passes... -->
<div class="sapling">🌿</div>
<!-- More time and proper conditions... -->
<div class="tree">🌳</div>
```

### Core Survival Loop
1. **🌱 Plant Seeds**: Start with basic resources
2. **💧 Find Water**: Essential for growth and survival
3. **🔥 Make Fire**: Warmth and protection from darkness
4. **🍖 Find Food**: Prevent starvation
5. **🏠 Build Shelter**: Protection from elements and creatures
6. **⚔️ Defend**: Survive hostile encounters

## 🛠️ Technology Stack

- **Frontend Framework**: [Nuxt 3](https://nuxt.com/)
- **Package Manager**: pnpm
- **Development**: Modern web technologies (specifics TBD)

*Technology choices are still being evaluated and will be updated as development progresses.*

## 🎮 Core Game Systems

### 🌱 Growth System
Entities follow natural progression:
- **Seeds** require water and time to become **saplings**
- **Saplings** need proper conditions to grow into **trees**
- **Trees** can be harvested for resources

### 🎒 Inventory System
Interact with your inventory through console commands:
```javascript
// Example interactions (final API TBD)
inventory.move('.torch', '#map .tile-x5-y3')
inventory.combine('.stick', '.cloth')
```

### 🎨 CSS Class Discovery
The game features a comprehensive set of predefined CSS classes:
- Logical naming for intuitive discovery
- Class combinations create emergent gameplay
- Experimentation and trial-and-error encouraged

### ⏰ Environmental Systems
- **Day/Night Cycle**: Affects visibility and creature behavior
- **Weather**: Rain helps growth, storms bring danger
- **Seasons**: Different resources and challenges


## 🎓 Educational Value

Markup Survival teaches web development concepts through gameplay:

### 🏗️ HTML Structure
- Semantic markup through entity creation
- Document structure and element relationships
- Data attributes for entity properties

### 🎨 CSS Mastery
- Class-based state management
- Logical class naming conventions
- Visual feedback through styling

### ⚡ JavaScript Skills
- DOM manipulation and querying
- Console-based interactions
- Object-oriented thinking

## 🎯 Target Audience

- **🎓 Students**: Learning web development interactively
- **👨‍💻 Developers**: Practicing skills in a survival context
- **🎮 Gamers**: Enjoying unique code-based gameplay mechanics

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🗺️ Roadmap

### 🎯 Version 1.0 (MVP)
- Core survival gameplay loop
- Basic crafting discovery system
- Day/night cycle with environmental effects
- Console-based interaction system

### 🚀 Future Versions
- Advanced crafting trees
- Weather system with seasonal changes
- Hostile creatures and combat mechanics
- Save/load functionality
- Creative/exploration modes

---

**Ready to survive through code?** 

Start your journey: `pnpm run dev` and open `http://localhost:3000`

*A solo project focused on survival through web development*
