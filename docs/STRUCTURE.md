# Markup Survival: Project Structure

*Lightweight Solo Development with Nuxt 3*

Simple, focused structure for efficient solo development of a survival game.

## Core Philosophy
- **Minimal Setup**: Only what's needed for survival gameplay
- **Solo-Friendly**: Easy to navigate and maintain alone
- **Nuxt 3 Standard**: Follow framework conventions
- **Survival-First**: Every file serves the core survival loop

## Directory Structure

```
markup-survival/
├── docs/                      # Developer documentation
│   ├── CONCEPT.md            # Game vision
│   ├── PHASES.md             # Development roadmap
│   ├── GAMEPLAY.md           # Mechanics guide
│   ├── API.md                # Console commands
│   └── STRUCTURE.md          # This file
├── components/               # Vue components
│   ├── Game.vue             # Main survival game
│   ├── Console.vue          # JavaScript command interface
│   ├── PlayerStats.vue      # Health/hunger display
│   └── World.vue            # DOM world container
├── composables/              # Game logic
│   ├── useGameEngine.ts     # Core survival loop
│   ├── useConsole.ts        # Command system
│   ├── usePlayer.ts         # Player stats
│   └── useEntities.ts       # Entity management
├── assets/                   # Styles and assets
│   ├── main.scss            # Game styles
│   └── entities.scss        # Entity visual classes
├── pages/                    # Nuxt pages
│   └── index.vue            # Game entry point
├── types/                    # TypeScript types
│   ├── game.ts              # Core types
│   └── entities.ts          # Entity types
├── data/                     # Game data
│   ├── entities.ts          # Entity definitions
│   ├── recipes.ts           # Crafting recipes
│   └── classes.ts           # CSS class effects
├── public/                   # Static files
├── README.md                # Setup instructions
├── package.json             # Dependencies
└── nuxt.config.ts           # Nuxt configuration
```

## Key Files Explained

### Core Game Logic
- **`composables/useGameEngine.ts`**: Main 60fps survival loop
- **`composables/useConsole.ts`**: JavaScript command interface
- **`composables/usePlayer.ts`**: Health/hunger/energy management
- **`composables/useEntities.ts`**: Entity creation and lifecycle

### Components (Minimal UI)
- **`Game.vue`**: Main game container
- **`Console.vue`**: Command input interface
- **`PlayerStats.vue`**: Survival stats display
- **`World.vue`**: DOM entity container

### Data Files
- **`data/entities.ts`**: All entity types (seed, tree, stone, etc.)
- **`data/recipes.ts`**: Crafting combinations
- **`data/classes.ts`**: CSS class definitions (.wet, .burning, etc.)

### Styling
- **`assets/main.scss`**: General game styles
- **`assets/entities.scss`**: Entity-specific CSS classes

## Development Workflow

### Starting Development
```bash
pnpm install
pnpm run dev
```

### Adding New Features
1. **New Entity**: Add to `data/entities.ts` and `assets/entities.scss`
2. **New Command**: Add to `composables/useConsole.ts`
3. **New Mechanic**: Update `composables/useGameEngine.ts`

### File Naming
- **Components**: PascalCase (`PlayerStats.vue`)
- **Composables**: camelCase with 'use' (`useGameEngine.ts`)
- **Types**: lowercase (`game.ts`)
- **Data**: lowercase (`entities.ts`)

## Essential Dependencies

```json
{
  "dependencies": {
    "nuxt": "^3.x",
    "typescript": "latest"
  },
  "devDependencies": {
    "@nuxt/devtools": "latest"
  }
}
```

## Solo Development Tips

### Keep It Simple
- Start with basic survival mechanics
- Add complexity gradually
- Don't over-engineer early
- Focus on playable over perfect

### File Organization
- Related code stays together
- Avoid deep nesting
- Clear, descriptive names
- Remove unused files quickly

### Testing Approach
- Manual testing during development
- Focus on survival gameplay flow
- Test discovery mechanics by playing
- Performance testing with many entities


