# Development Guide: Six-Days

## Prerequisites

### Required Software

- **Unreal Engine 5.5**: Download from Epic Games Launcher
- **Visual Studio 2022** (Windows) or **Xcode** (macOS): For C++ development
- **Git**: For version control
- **Git LFS**: For handling large binary assets

### Recommended Hardware

- **CPU**: 8+ cores recommended
- **RAM**: 32GB minimum, 64GB recommended
- **GPU**: RTX 3060 or equivalent minimum (RTX 4000 series recommended for Lumen/Nanite)
- **Storage**: 100GB+ SSD space for engine and project

## Project Setup

### Initial Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/EthanZhu1022/Six-Days.git
   cd Six-Days
   ```

2. **Initialize Git LFS** (if not already done)
   ```bash
   git lfs install
   git lfs pull
   ```

3. **Generate Project Files**
   - Right-click on `SixDays.uproject` (when created) and select "Generate Visual Studio project files"
   - Or use command line:
     ```bash
     "C:\Program Files\Epic Games\UE_5.5\Engine\Build\BatchFiles\Build.bat" SixDaysEditor Win64 Development -project="SixDays.uproject" -projectfiles
     ```

4. **Open in Unreal Engine**
   - Launch Unreal Engine 5.5
   - Open `SixDays.uproject`
   - Allow shader compilation to complete (first time takes significant time)

## Project Structure

```
Six-Days/
├── Content/                    # Game assets and blueprints
│   ├── Characters/            # Player and NPC characters
│   ├── Environments/          # Level assets and materials
│   ├── Audio/                 # Sound effects and music
│   ├── UI/                    # User interface elements
│   ├── Blueprints/            # Game logic blueprints
│   └── Philosophical/         # Theme-specific content
├── Source/                     # C++ source code
│   └── SixDays/               # Main game module
├── Config/                     # Configuration files
├── Plugins/                    # Third-party and custom plugins
├── Documentation/              # Additional documentation
├── README.md                   # Project overview
├── GAME_DESIGN.md             # Game design document
├── PHILOSOPHY.md              # Philosophical foundation
└── DEVELOPMENT.md             # This file
```

## Development Philosophy

### Aligning Code with Theme

Our development practices reflect the game's philosophical themes:

1. **Embrace Emergence**: Write systems that allow unexpected behaviors
2. **Question Assumptions**: Challenge conventional game development practices
3. **Iterative Deconstruction**: Be willing to break and rebuild systems
4. **Meaningful Experimentation**: Try unconventional approaches that serve the theme

### Code Principles

- **Flexible Systems**: Prefer loose coupling and emergent complexity
- **Readable Chaos**: Code can be unconventional but should remain understandable
- **Philosophical Comments**: Explain not just what and how, but why in context of themes
- **Refactor Boldly**: Don't be afraid to collapse and rebuild

## Key Technical Areas

### 1. World State System

Manages the progressive collapse of order:

```cpp
// Example approach
class AWorldStateManager
{
    float OrderLevel;  // 1.0 = complete order, 0.0 = complete chaos
    void UpdateSystemReliability(float DeltaTime);
    void PropagateCollapseEffects();
};
```

### 2. Navigation Ambiguity

Implements unreliable guidance systems:

- Custom nav mesh that degrades over time
- Procedural landmark generation
- Player intuition tracking system

### 3. Identity Flux System

Handles fluid player character identity:

- Dynamic ability system
- Visual transformation pipeline
- Narrative state machine with fuzzy transitions

### 4. Emergent Event System

Generates philosophical encounters:

- Event probability based on player actions and world state
- NPC behavior driven by philosophical archetypes
- Environmental storytelling triggers

### 5. Temporal Cycle Manager

Controls the six-day structure:

- Day progression with unique characteristics
- Persistent player knowledge across cycles
- Procedural variation in each cycle

## UE5.5 Feature Utilization

### Nanite

- Use for detailed, degrading environments
- Implement visual collapse through material parameters
- High-poly environmental storytelling assets

### Lumen

- Dynamic lighting reflects world state
- Symbolic use of light/darkness
- Performance-friendly global illumination

### MetaSounds

- Procedural audio that fragments and reassembles
- Musical representation of philosophical states
- Spatial audio for environmental narrative

### Chaos Physics

- Literal breakdown of structures
- Physics-driven environmental storytelling
- Emergent interactions from physics systems

### World Partition

- Large, explorable world
- Streaming for seamless experience
- Memory management for complex systems

## Workflow Guidelines

### Version Control

```bash
# Create feature branch
git checkout -b feature/your-feature-name

# Make changes, commit with descriptive messages
git add .
git commit -m "Implement [feature]: Brief description of changes"

# Push to remote
git push origin feature/your-feature-name

# Create pull request for review
```

### Asset Management

- Use consistent naming conventions
- Store large assets with Git LFS
- Organize by function and theme
- Document philosophical intent in asset metadata

### Blueprint vs C++

- **C++**: Core systems, performance-critical code, reusable components
- **Blueprints**: Rapid prototyping, designer-friendly logic, content-specific behavior
- Both are valid; use what serves the implementation best

### Testing Approach

Since traditional testing may not fully capture philosophical goals:

1. **Technical Testing**: Verify systems work as intended
2. **Experiential Testing**: Does it create the intended philosophical experience?
3. **Emergent Behavior Testing**: Observe unplanned interactions
4. **Player Interpretation Testing**: Playtest with target audience

## Building and Running

### Development Build

```bash
# Windows
"C:\Program Files\Epic Games\UE_5.5\Engine\Build\BatchFiles\Build.bat" SixDaysEditor Win64 Development

# Launch editor
"C:\Program Files\Epic Games\UE_5.5\Engine\Binaries\Win64\UnrealEditor.exe" "SixDays.uproject"
```

### Shipping Build

```bash
# Package for target platform via Editor
# Edit > Project Settings > Packaging
# Then: File > Package Project > [Platform]
```

## Common Development Tasks

### Adding New Philosophical Content

1. Document the concept in PHILOSOPHY.md
2. Design gameplay expression in GAME_DESIGN.md
3. Implement technical systems in C++/Blueprint
4. Create supporting assets
5. Playtest for philosophical resonance

### Implementing System Degradation

1. Identify target system (UI, navigation, etc.)
2. Create degradation parameters
3. Link to world state manager
4. Test at various order levels
5. Ensure graceful transitions

### Creating Emergent Events

1. Define philosophical purpose
2. Design trigger conditions
3. Implement with flexibility for emergence
4. Avoid over-constraining player response
5. Observe unexpected interactions

## Performance Considerations

- Profile regularly (UE5 Insights, stat commands)
- Balance philosophical goals with technical constraints
- Optimize procedural systems
- Use LODs and streaming effectively
- Monitor memory usage with complex state systems

## Debugging Philosophy

The game's theme informs even debugging:

- Some "bugs" might be features (productive glitches)
- Distinguish between harmful errors and meaningful chaos
- Document interesting emergent behaviors
- Consider whether fixes serve or undermine themes

## Documentation Standards

### Code Comments

```cpp
// Technical explanation
// Philosophical intent: [Why this serves the theme]
// Emergent potential: [What unexpected behaviors might arise]
```

### Commit Messages

```
[Category] Brief description

Extended explanation of changes and philosophical reasoning if relevant.

Philosophical impact: [How this affects theme expression]
```

## Resources

### Unreal Engine 5.5

- [Official Documentation](https://docs.unrealengine.com/5.5)
- [UE5 Learning Portal](https://dev.epicgames.com/community/learning)
- [UE5 Forums](https://forums.unrealengine.com)

### Philosophical References

- See PHILOSOPHY.md for primary philosophical influences
- Research existentialism, post-structuralism, and absurdism
- Study games that explore similar themes

### Community

- Project Discord: [TBD]
- Development Blog: [TBD]
- Issue Tracker: GitHub Issues

## Contributing

We welcome contributions that align with the project's philosophical vision:

1. Read PHILOSOPHY.md and GAME_DESIGN.md
2. Discuss major changes in issues before implementing
3. Follow existing code style and structure
4. Include philosophical reasoning in pull requests
5. Be open to unconventional approaches that serve the theme

## Troubleshooting

### Common Issues

**Shader compilation takes forever**
- Expected on first launch
- Subsequent launches are faster
- Use "Pause" to defer compilation if needed

**Git LFS assets missing**
- Run `git lfs pull`
- Verify Git LFS is installed
- Check .gitattributes configuration

**Project won't open**
- Verify UE5.5 is installed
- Check project file isn't corrupted
- Try generating project files again

**Performance issues**
- Check GPU drivers are updated
- Verify hardware meets requirements
- Disable Lumen/Nanite for testing if needed
- Use stat commands to identify bottlenecks

## Contact

For questions or issues:
- GitHub Issues: [Project issues page]
- Project Lead: [Contact info TBD]

## License

See LICENSE file for project licensing details.

---

*"In development as in gameplay, we embrace the collapse of rigid methodologies and affirm the existence of creative emergence."*
