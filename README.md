# copalibre-modules

The curated community module repository for [CopaLibre](https://github.com/SebaSOFT/copalibre) disciplines and tournament profiles.

`copalibre module add <alias>[@range]` resolves and installs disciplines and profiles from this repository by default. Operators can install any community discipline or tournament profile with a single command.

Modules are pure data (declarative JSON), never executable code: each module descriptor references a fixed, core-owned schema and vocabulary of rule actions, conditions, and statistics.

---

## Bundled Community Disciplines

This repository ships 22 production community disciplines, 1 reference example, and 11 tournament profiles:

| Discipline | Type | Segments | Scoring & Events | Wallpaper Asset |
| :--- | :--- | :--- | :--- | :--- |
| **American Football** (`american-football`) | Team (11v11) | 4 Quarters (15m) + Overtime | Touchdown (6), Field Goal (3), Safety (2), PAT (1), 2pt Conv (2) | `american-football-01.jpg` (2560×1440) |
| **Baseball** (`baseball`) | Team (9v9) | 9 Innings + Extra Innings | Runs, Hits, Errors, Strikeouts, Home Runs | `baseball-01.jpg` (2560×1440) |
| **Basketball** (`basketball`) | Team (5v5) | 4 Quarters (10m) + Overtime | 2pt Field Goal, 3pt Field Goal, Free Throw, Personal Fouls | `basketball-01.jpg` (2560×1440) |
| **Beach Volleyball** (`beach-volleyball`) | Team (2v2) | Sets (Best of 3, 21pt / 15pt) | Set Points, 2-point margin win condition, Ace, Attack Kill | `beach-volleyball-01.jpg` (2560×1440) |
| **Boxing** (`boxing`) | Individual (1v1) | 12 Rounds (3m) | Decision, Knockdown, KO/TKO stoppage outcome workflows | `boxing-01.jpg` (2560×1440) |
| **Counter-Strike 2** (`counter-strike-2`) | Team (5v5) | MR12 Rounds + Overtime | Round Won, Bomb Plant, Bomb Defuse, Frags, Headshots | `counter-strike-2-01.jpg` (2560×1440) |
| **Cricket** (`cricket`) | Team (11v11) | 2 Innings / Overs | Runs, Wickets, 4s, 6s, Extras, Bowling Maidens | `cricket-01.jpg` (2560×1440) |
| **Cycling Race** (`cycling-race`) | Individual / Team | Stages / Laps / Heats | Split times, finish times, lowest time aggregation | `cycling-race-01.jpg` (2560×1440) |
| **DOTA 2** (`dota-2`) | Team (5v5) | Maps / Games (Best of 3/5) | Map Won, Tower Kill, Roshan Kill, Kills, Net Worth | `dota-2-01.jpg` (2560×1440) |
| **Field Hockey** (`field-hockey`) | Team (11v11) | 4 Quarters (15m) + Shootout | Field Goal, Penalty Corner, Penalty Stroke, Cards | `field-hockey-01.jpg` (2560×1440) |
| **Golf** (`golf`) | Individual | 18 Holes (Stroke Play) | Hole strokes, Pars, Birdies, Eagles, Bogeys, lowest strokes | `golf-01.jpg` (2560×1440) |
| **Handball** (`handball`) | Team (7v7) | 2 Halves (30m) + Overtime | 1pt Goals, 7m Penalty Throw, 2-Minute Suspension, Cards | `handball-01.jpg` (2560×1440) |
| **Horse Racing** (`horse-racing`) | Individual | Heats & Finals (Turf / Dirt) | Finish timing, fastest time win condition | `horse-racing-01.jpg` (2560×1440) |
| **Ice Hockey** (`ice-hockey`) | Team (6v6) | 3 Periods (20m) + OT + Shootout| Goals, Assists, Saves, Penalties (3-2-1-0 standings points) | `ice-hockey-01.jpg` (2560×1440) |
| **League of Legends** (`league-of-legends`)| Team (5v5) | Maps / Games (Best of 3/5) | Map Won, Turret Kill, Baron/Dragon Kill, Kills | `league-of-legends-01.jpg` (2560×1440) |
| **Orbital Frisbee** (`orbital-frisbee`) | Team (5v5) | 2 Halves | Reference minimal discipline without assets | *None* (zero-asset reference) |
| **Quake 3 Arena** (`quake-3-arena`) | Individual / Team | Timed Fragmatch (15m) | Fraglimit, Railgun/Rocket kills, weapon statistics | `quake-3-arena-01.jpg` (2560×1440) |
| **Quake Champions** (`quake-champions`) | Individual / Team | Crucible / Arena Match | Frags, Ability kills, Medal statistics | `quake-champions-01.jpg` (2560×1440) |
| **Rocket League** (`rocket-league`) | Team / Individual | 5m Timed + Golden Goal OT | Goals, Saves, Assists, Shots on Goal, Epic Saves | `rocket-league-01.jpg` (2560×1440) |
| **Rugby** (`rugby`) | Team (15v15) | 2 Halves (40m) + Extra Time | Try (5), Conversion (2), Penalty Goal (3), Drop Goal (3) | `rugby-01.jpg` (2560×1440) |
| **Swimming Race** (`swimming-race`) | Individual | Heats & Finals (50m–1500m) | Lane times, split times, fastest time aggregation | `swimming-race-01.jpg` (2560×1440) |
| **VALORANT** (`valorant`) | Team (5v5) | MR12 Rounds + Overtime | Spike Plant, Spike Defuse, Round Won, Frags, Agent Roles | `valorant-01.jpg` (2560×1440) |
| **Volleyball** (`volleyball`) | Team (6v6) | Sets (Best of 5, 25pt / 15pt) | Set Points, 2-point margin win condition, Ace, Block | `volleyball-01.jpg` (2560×1440) |

*(First-party core disciplines `football` and `tennis` are bundled directly inside `@copalibre/module-catalogue`).*

---

## Bundled Community Tournament Profiles

| Profile Alias | Name | Stages & Formats | Points | Target Disciplines |
| :--- | :--- | :--- | :--- | :--- |
| **`weekend-cup`** | Weekend Cup | 1: `round-robin` | 3-1-0 | Reference round-robin cup |
| **`double-elimination-bracket`** | Double-Elimination Bracket | 1: `double-elimination` | 0-0-0 | Esports, Combat, Racket, Invasion sports (20 disciplines) |
| **`heats-and-finals`** | Heats to Finals Championship | 1: `heats`, 2: `heats` | 0-0-0 | Cycling, Swimming, Horse Racing, Golf, Arena FPS (6 disciplines) |
| **`open-grand-prix`** | Open Grand Prix | 1: `free-for-all` | 0-0-0 | Racing classics, Golf stroke play, Time trials, FFA Deathmatch |
| **`esports-gsl-groups-to-playoffs`** | GSL Groups to Double-Elimination Playoffs | 1: `round-robin`, 2: `double-elimination` | 3-1-0 | Major esports (CS2, Valorant, Dota 2, LoL, Rocket League) |
| **`single-leg-league`** | Single Round-Robin League | 1: `round-robin-single-leg` | 3-1-0 | Single-round leagues, Six Nations, Festivals (13 disciplines) |
| **`ice-hockey-three-point-cup`** | Ice Hockey 3-Point Cup & Playoffs | 1: `round-robin`, 2: `single-elimination` | 3-1-0 | Ice Hockey, Field Hockey, Handball, Rocket League |
| **`rugby-bonus-point-championship`** | Rugby Union 4-Point Bonus Championship | 1: `round-robin`, 2: `single-elimination` | 4-2-0 | Rugby Union, American Football, Basketball, Volleyball |
| **`cricket-championship-cup`** | Cricket Limited-Overs Cup | 1: `round-robin`, 2: `single-elimination` | 2-1-0 | Cricket, Baseball (Runs & Wickets tiebreakers) |
| **`baseball-pool-playoff`** | Baseball Pool Play to Championship Playoff | 1: `round-robin-single-leg`, 2: `single-elimination` | 1-0-0 | Baseball, Cricket (Runs & Home Runs tiebreakers) |
| **`arena-ffa-deathmatch`** | Arena Free-For-All Deathmatch Championship | 1: `heats`, 2: `free-for-all` | 0-0-0 | Quake III Arena, Quake Champions (Frags & Deaths tiebreakers) |

---

## CopaLibre Module Architecture & Features

Every module in this repository leverages the full descriptor schema from `@copalibre/domain` and `@copalibre/rules`:

### 1. Structure & Layout
```
disciplines/<alias>/
  manifest.json   — kind, alias, version, attribution, requiresCopalibre, declared assets
  artifact.json   — the complete discipline descriptor document
  assets/         — background wallpaper images declared in manifest.json (<alias>-01.jpg)
profiles/<alias>/
  manifest.json
  artifact.json   — the tournament profile descriptor document
  assets/
```

### 2. Supported Descriptor Capabilities
- **i18n Localization**: Localized names, descriptions, segment titles, event labels, and standings table headers (`en`, `es`).
- **Participant Types & Rosters**: Strict `team`, `individual`, or dual constraints with `minPlayers`, `maxPlayers`, `maxSubstitutes`, and `rosterRoles` (Captain, Goalkeeper, In-Game Leader, etc.).
- **Segment Definitions**: Timed or untimed segments (`half`, `quarter`, `period`, `inning`, `set`, `round`, `map`, `overtime`, `penalty-shootout`) with default duration seconds.
- **Atomic Domain Events & Effects**: Scoring deltas, statistic mutations, assist attribution, and payload schemas with branching `outcome-choice` workflows.
- **Statistics & Collectors**: Domain statistics aggregated by `sum`, `count`, `max`, `min`, or `latest` across match or competition stage granularities.
- **Custom Table Layouts**: Standings projections with customizable columns, headers, computed differential formulas, and multi-key tiebreak sorting.
- **Neuron-JS Win Conditions**: Declarative rule scripts (`winMatch`, `simple_rule`, `requireMargin`, etc.) evaluated by the rule compiler.
- **Governance & Field Policies**: Mutation permissions (`safe`, `blocked_after_results`, `requires_rebuild`) ensuring tournament integrity.
- **Atmospheric Background Wallpapers**: 2560×1440 progressive widescreen JPEGs rendered behind tables and live broadcasts at 10% opacity with dynamic Gaussian blur.

---

## CLI Usage

### Installing a Discipline
```bash
copalibre module add basketball@^1.0.0
copalibre module add valorant@^1.0.0
copalibre module add rocket-league@^1.0.0
```

### Installing a Tournament Profile
```bash
copalibre module add double-elimination-bracket@^1.0.0
copalibre module add heats-and-finals@^1.0.0
copalibre module add esports-gsl-groups-to-playoffs@^1.0.0
```

### Listing Installed Modules
```bash
copalibre module list
```

### Removing a Module
```bash
copalibre module remove basketball
copalibre module remove double-elimination-bracket
```

---

## Contributing a Module

1. Fork this repository.
2. Add your module under `disciplines/<your-alias>/` or `profiles/<your-alias>/`, following the layout above.
3. Validate locally:
   ```bash
   node ../copalibre/scripts/validate-module-repository.mjs .
   ```
4. Open a pull request. CI runs the exact same validation engine as `copalibre module add` at install time:
   - Manifest and artifact schema conformance
   - Registry reference vetting for all actions/conditions/parameters
   - Neuron-JS rule compilation
   - Asset format (JPEG/PNG), dimensions (max 2560×1440), and byte size (max 2 MB)
   - Alias namespace uniqueness (no collisions with first-party catalogue)
5. Once merged, tag the release commit as `<alias>@<version>` (e.g., `basketball@1.0.0`).

---

## License

The tooling and documentation in this repository are MIT licensed (see `LICENSE`). Each module's content carries its own licence, declared in its `manifest.json`/`artifact.json` `attribution.licence` field (typically `AGPL-3.0-only` or `CC0-1.0`).
