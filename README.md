# 🏰 Dungeon Shooter

![Unity](https://img.shields.io/badge/Unity-2D-000000?style=for-the-badge&logo=unity&logoColor=white)
![C#](https://img.shields.io/badge/C%23-73.1%25-239120?style=for-the-badge&logo=csharp&logoColor=white)
![ShaderLab](https://img.shields.io/badge/ShaderLab-22.9%25-purple?style=for-the-badge)
![HLSL](https://img.shields.io/badge/HLSL-4%25-blue?style=for-the-badge)

> A fast-paced 2D top-down action shooter game built with Unity. Battle through hordes of enemies, collect gold, purchase powerful weapons, and defeat the dungeon boss to claim victory!

## 🎮 Game Overview

**Dungeon Shooter** is an action-packed 2D shooter where players must navigate through a dangerous dungeon filled with enemies. The game features:

- ⚔️ **Intense Combat**: Fight melee and ranged enemies with responsive shooting mechanics
- 🏃 **Dash Mechanic**: Evade attacks with a quick dash ability
- 🔫 **Weapon System**: Start with a pistol, unlock double pistols and rifles
- 💰 **Economy System**: Collect gold from defeated enemies to purchase upgrades
- 🧪 **Health Potions**: Buy and use potions to restore health
- 👹 **Epic Boss Fight**: Face the dungeon boss with multiple attack patterns
- 🏪 **In-Game Shop**: Purchase weapons and items between combat

## 🖼️ Screenshots

| Gameplay | Boss Fight | Shop |
|----------|------------|------|
| Top-down shooter action | Epic boss encounter | Weapon & item purchases |

## 🏗️ Game Architecture

```
┌─────────────────────────────────────────────────────────────────────┐
│                        DUNGEON SHOOTER                               │
└─────────────────────────────────────────────────────────────────────┘
                                │
    ┌───────────────────────────┼───────────────────────────┐
    │                           │                           │
    ▼                           ▼                           ▼
┌─────────────┐         ┌─────────────┐         ┌─────────────────┐
│   PLAYER    │         │   ENEMIES   │         │      BOSS       │
│   SYSTEM    │         │   SYSTEM    │         │     SYSTEM      │
├─────────────┤         ├─────────────┤         ├─────────────────┤
│ • Movement  │         │ • Melee AI  │         │ • Multi-Phase   │
│ • Shooting  │         │ • Ranged AI │         │ • Skill Attacks │
│ • Dash      │         │ • Pathfind  │         │ • Enemy Spawns  │
│ • Health    │         │ • Knockback │         │ • Bullet Hell   │
│ • Inventory │         │ • Gold Drop │         │ • Melee Attacks │
└──────┬──────┘         └──────┬──────┘         └────────┬────────┘
       │                       │                         │
       └───────────────────────┼─────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────────────┐
│                         CORE SYSTEMS                                 │
├─────────────────────────────────────────────────────────────────────┤
│                                                                      │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌────────────┐ │
│  │   Weapons   │  │    Shop     │  │   Audio     │  │   UI/UX    │ │
│  │   System    │  │   System    │  │  Manager    │  │  System    │ │
│  ├─────────────┤  ├─────────────┤  ├─────────────┤  ├────────────┤ │
│  │ • Pistol    │  │ • Buy Items │  │ • SFX       │  │ • Health   │ │
│  │ • DoublePis │  │ • Buy Wpns  │  │ • Music     │  │ • Gold UI  │ │
│  │ • Rifle     │  │ • Equip     │  │ • Hit FX    │  │ • Potion   │ │
│  │ • Fire Rate │  │ • Potions   │  │ • Gun FX    │  │ • Menus    │ │
│  └─────────────┘  └─────────────┘  └─────────────┘  └────────────┘ │
│                                                                      │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌────────────┐ │
│  │   Damage    │  │  Knockback  │  │   Visual    │  │   Scene    │ │
│  │  Interface  │  │   System    │  │   Effects   │  │  Manager   │ │
│  ├─────────────┤  ├─────────────┤  ├─────────────┤  ├────────────┤ │
│  │ IDamageble │  │ • Force     │  │ • Flash FX  │  │ • MainMenu │ │
│  │ • Player   │  │ • Duration  │  │ • Hit FX    │  │ • Gameplay │ │
│  │ • Enemy    │  │ • Direction │  │ • Trail FX  │  │ • GameOver │ │
│  │ • RangedE  │  │             │  │ • Particles │  │ • WinScreen│ │
│  └─────────────┘  └─────────────┘  └─────────────┘  └────────────┘ │
│                                                                      │
└─────────────────────────────────────────────────────────────────────┘
```

## 🛠️ Tech Stack

| Technology | Version | Purpose |
|------------|---------|---------|
| **Unity** | 2D | Game Engine |
| **C#** | - | Programming Language |
| **ShaderLab** | - | Custom Shaders |
| **HLSL** | - | Shader Programming |
| **TextMesh Pro** | - | UI Text Rendering |

## 📁 Project Structure

```
DungeonShooter/
├── 📂 Assets/
│   ├── 📂 Scripts/                 # Game Scripts
│   │   ├── player.cs               # Player controller & mechanics
│   │   ├── enemy.cs                # Melee enemy AI
│   │   ├── rangedEnemy.cs          # Ranged enemy AI
│   │   ├── shooting.cs             # Player shooting mechanics
│   │   ├── bullet.cs               # Player bullet behavior
│   │   ├── weapon.cs               # Weapon ScriptableObject
│   │   ├── gun_Aim.cs              # Weapon aiming system
│   │   ├── Shop.cs                 # In-game shop system
│   │   ├── Gold.cs                 # Gold pickup collectible
│   │   ├── HealthBar.cs            # Health bar UI component
│   │   ├── SimpleFlash.cs          # Damage flash effect
│   │   ├── MainMenu.cs             # Main menu controller
│   │   ├── IDamageble.cs           # Damage interface
│   │   │
│   │   └── 📂 boss/                # Boss-specific scripts
│   │       ├── boss.cs             # Boss AI & attacks
│   │       ├── BossBullet.cs       # Boss projectile
│   │       ├── BossSkill1.cs       # Boss skill 1 (AoE)
│   │       └── BossSkill2.cs       # Boss skill 2 (Bullet spread)
│   │
│   ├── 📂 Prefabs/                 # Reusable game objects
│   ├── 📂 Sprites/                 # 2D graphics
│   ├── 📂 Animations/              # Character animations
│   ├── 📂 Audio/                   # Sound effects & music
│   ├── 📂 Scenes/                  # Game scenes
│   ├── 📂 Materials/               # Materials & shaders
│   └── 📂 TextMesh Pro/            # Text rendering assets
│
├── 📂 Packages/                    # Unity packages
├── 📂 ProjectSettings/             # Unity project settings
└── 📄 README.md                    # This file
```

## 🎯 Core Systems

### 🕹️ Player System

The player controller implements comprehensive movement and combat mechanics:

```csharp
public class player : MonoBehaviour, IDamageble
{
    // Movement
    public float moveSpeed = 5f;
    private float dashSpeed = 10f;
    private float dashCooldown = 1f;
    
    // Combat
    public GameObject[] weaponObjects;
    public Weapon[] allweapons;
    
    // Health & Resources
    public int gold = 0;
    public int healthPotionCount = 0;
}
```

**Features:**
- WASD/Arrow key movement with physics-based Rigidbody2D
- Mouse-aim weapon targeting
- Space bar dash with cooldown and trail effect
- Health system with damage flash effects
- Gold collection and potion inventory
- Multiple weapon support with switching

### ⚔️ Weapon System

Weapons are defined as ScriptableObjects for easy customization:

```csharp
public enum WeaponType
{
    Pistol,
    DoublePistol,
    Rifle
}

[CreateAssetMenu(fileName = "New Weapon", menuName = "Weapon")]
public class Weapon : ScriptableObject
{
    public WeaponType weaponType;
    public GameObject weaponPrefab;
    public float fireRate;
}
```

| Weapon | Fire Rate | Special |
|--------|-----------|---------|
| 🔫 Pistol | Normal | Starting weapon |
| 🔫🔫 Double Pistol | Fast | Fires two bullets |
| 🎯 Rifle | Slow | High damage |

### 👹 Enemy AI System

#### Melee Enemy
```csharp
public class enemy : MonoBehaviour, IDamageble
{
    private float triggerDistance = 14f;
    private float speed = 4.5f;
    
    // Chases player when in range
    // Deals contact damage
    // Drops gold on death
}
```

#### Ranged Enemy
```csharp
public class rangedEnemy : MonoBehaviour, IDamageble
{
    public float fireRate = 1.2f;
    public float distanceToShoot = 14f;
    
    // Keeps distance from player
    // Shoots projectiles
    // Drops gold on death
}
```

### 👑 Boss System

The dungeon boss features multiple attack patterns:

```csharp
public class boss : MonoBehaviour
{
    public int maxHealth = 100;
    public float spawnRate;          // Spawns minions
    public float skill1Rate;         // AoE attack
    public float skill2Rate;         // Bullet spread
    public float meleeRate;          // Close combat
}
```

**Boss Abilities:**
1. **Minion Spawn**: Summons melee and ranged enemies
2. **Skill 1 (AoE)**: Area damage at player position
3. **Skill 2 (Bullets)**: Directional projectile attack
4. **Melee Attack**: Contact damage with knockback

### 🏪 Shop System

In-game store for purchasing items and weapons:

```csharp
public class Shop : MonoBehaviour
{
    // Item Prices
    private int healthPotionCost = 5;
    private int doublePistolCost = 20;
    private int rifleCost = 40;
}
```

| Item | Cost | Description |
|------|------|-------------|
| 🧪 Health Potion | 5 gold | Restores 50 HP |
| 🔫🔫 Double Pistol | 20 gold | Dual-wield pistols |
| 🎯 Rifle | 40 gold | High-power weapon |

### 💥 Damage System

Unified damage interface for all damageable entities:

```csharp
public interface IDamageble
{
    float health { get; set; }
    bool isKnocking { get; set; }
    float knockbackDuration { get; set; }
    SimpleFlash flashEffect { get; set; }
    
    void takeDamage(float damage, Vector2 direction, float knockbackForce);
    IEnumerator Knockback(Vector2 direction, float knockbackForce);
}
```

**Implemented by:**
- ✅ Player
- ✅ Melee Enemy
- ✅ Ranged Enemy
- ✅ Boss (custom implementation)

## 🎮 Controls

| Key | Action |
|-----|--------|
| `W/A/S/D` or `↑/←/↓/→` | Movement |
| `Mouse` | Aim weapon |
| `Left Click` | Shoot |
| `Space` | Dash |
| `E` | Use health potion |
| `B` | Open/close shop |
| `ESC` | Pause menu |

## ✨ Visual Effects

### Damage Flash
When entities take damage, a material swap creates a flash effect:

```csharp
public class SimpleFlash : MonoBehaviour
{
    [SerializeField] private Material flashMaterial;
    [SerializeField] private float duration;
    
    public void Flash()
    {
        StartCoroutine(FlashRoutine());
    }
}
```

### Dash Trail
Trail renderer attached to player during dash for visual feedback.

### Hit Effects
Particle systems instantiated on bullet impacts:
- Enemy hit effect
- Wall hit effect
- Boss hit effect

## 🎵 Audio System

Centralized audio management with singleton pattern:

```csharp
public class AudioManager
{
    public static AudioManager instance;
    
    public void PlayMusic(AudioClip clip);
    public void BulletHitSound(AudioClip clip);
    public void BulletMapHitSound(AudioClip clip);
    public void EnemyGunSound(AudioClip clip);
    public void CoinSound(AudioClip clip);
}
```

## 🚀 Getting Started

### Prerequisites
- Unity 2021.3 LTS or newer
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/kerem02/DungeonShooter.git
   ```

2. **Open in Unity**
   - Launch Unity Hub
   - Click "Open" and select the cloned folder
   - Wait for Unity to import all assets

3. **Play the game**
   - Open `Scenes/MainMenu` in the Project window
   - Press the Play button in Unity Editor
   - Click "Start Game" to begin

### Building the Game

1. Go to `File > Build Settings`
2. Add scenes to build:
   - MainMenu
   - SampleScene (gameplay)
3. Select target platform
4. Click "Build"

## 🎯 Game Design Patterns

### Design Patterns Used

| Pattern | Implementation |
|---------|----------------|
| **Singleton** | AudioManager for global audio control |
| **Interface** | IDamageble for polymorphic damage handling |
| **ScriptableObject** | Weapon data definition |
| **Factory** | Bullet/Enemy instantiation |
| **State Machine** | Boss behavior states |
| **Observer** | UI updates on health/gold changes |
| **Coroutine** | Async operations (knockback, dash, flash) |

## 🎓 Technical Highlights

### Physics-Based Movement
- Rigidbody2D for smooth, physics-respecting movement
- Velocity-based movement for consistent speed
- Force-based knockback system

### Modular Architecture
- Clear separation between systems
- Interface-based damage handling
- ScriptableObjects for data-driven design

### Performance Considerations
- Object pooling potential for bullets
- Efficient trigger-based collision detection
- Optimized update loops with FixedUpdate for physics

## 📊 Code Quality

- ✅ Well-documented code with comments
- ✅ Consistent naming conventions
- ✅ Modular and reusable components
- ✅ Interface-based design for extensibility
- ✅ ScriptableObjects for data-driven design

## 🔮 Future Improvements

- [ ] Multiple dungeon levels
- [ ] More weapon varieties
- [ ] Additional boss fights
- [ ] Save/Load system
- [ ] Procedural level generation
- [ ] Online leaderboards
- [ ] Power-ups and abilities
- [ ] More enemy types

## 📝 License

This project is developed for educational purposes.

---

<p align="center">
  <b>🏰 Dungeon Shooter</b><br>
  <i>A 2D Action Shooter Game</i><br><br>
  Unity | C# | 2D Game Development | AI | Combat Systems
</p>
