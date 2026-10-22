# Monster Hunt: Love Beyond the Crown

A browser trivia-battle game built with plain HTML, CSS and JavaScript. No frameworks, no build step, no npm install.

**Story:** Cedric, a low-born monster hunter, crosses four regions to win back Sylvaine, a noble's daughter taken away by her father. Each region is guarded by a boss who can only be beaten by answering trivia.

| Region | Boss | Trivia theme |
|---|---|---|
| Forest | Goblin King | Geography |
| Wetland | Ogre | Marine life |
| Desert | Skeleton King | Food |
| Mountains | Dragon King | Animals |

## How to run it

1. Put the whole project in one folder, with the `assets/` folder next to the three files (see [Folder structure](#folder-structure)).
2. Open the folder in VS Code and install the **Live Server** extension (Ritwick Dey).
3. Right-click `index.html` and choose **Open with Live Server**.

You can also double-click `index.html` to open it in a browser. Live Server is recommended because it auto-reloads on save and serves audio files more reliably.

An internet connection is only needed for the Google Fonts (Cinzel, Cormorant Garamond, Tangerine, Poppins). Without it the game still works and falls back to default fonts.

## How to play

1. On the title screen, click anywhere to enter the main menu.
2. **New Game** plays the intro story, then opens the map. **Continue** resumes from your last saved region.
3. Pick an unlocked region on the map. Regions unlock in order.
4. In battle, a question appears and the answer is shown as empty letter boxes. Tap letter tiles to fill them in. The tile board contains the answer's letters plus random filler letters.
   - **Undo** removes the last letter. **Clear** removes all of them.
   - The answer is checked automatically when every box is filled.
5. A correct answer damages the boss. A wrong answer, or running out of time, makes the boss hit back.
6. Reduce the boss to 0 HP to clear the region and choose a bonus. Defeat the Dragon King to see the ending.
7. If Cedric reaches 0 HP, use **Retry Battle** to try the region again.

### Damage and timing

| | Value |
|---|---|
| Easy question | 10 damage |
| Medium question | 20 damage |
| Hard question | 30 damage |
| Boss counterattack | 15 damage |
| Time per question | 20 seconds (can be turned off in Settings) |

### Bonuses (pick 1 of 3 random choices after each region)

- **+2 Hints:** the Hint button fills in the next correct letter, up to 2 times.
- **Double Hit:** your next correct answer deals double damage.
- **+10% Life:** restores 10 HP (max 100).
- **Shield:** blocks the boss's next counterattack.
- **Extra Turn:** after a correct answer you answer again before the boss gets a turn.

### Controls

- **Esc** (or the ⏸ button) pauses during battle.
- **☰** in the battle top bar opens the Quest Log. The timer is frozen while it is open.
- **Settings** (Option on the main menu, or from the pause menu): music volume, sound effects volume, question timer on/off, and text size.

## Save system

Progress is saved automatically in the browser's `localStorage` when you start a game and when you defeat a boss. It stores **which regions you have completed**, so Continue returns you to the map with those regions cleared. HP, hints and unused bonuses are **not** saved and reset to defaults on Continue.

To wipe your save, clear the site's data in your browser, or run `localStorage.removeItem("monsterHuntSave")` in the browser console.

## Folder structure

```
monster-hunt-game/
├── index.html      Structure of every screen (landing, menu, map, quest log, story, battle, bonus, victory, game over, pause, settings)
├── style.css       All styling; design tokens and clash-animation timings are CSS variables at the top
├── script.js       Game state, story slides, question banks, battle logic, audio, save/load
├── README.md
└── assets/         Images, GIFs and audio (must exist, see below)
```

### Required assets

The game loads these from `assets/`. **File names are case-sensitive** once the game is hosted online.

**Images:** `landing.png`, `logo.png`, `story-art.png`, `cedric.png`, `goblin.png`, `ogre.png`, `skeleton.png`, `dragon.png`, and story pictures `1.png` to `16.png`.

**Backgrounds (GIF):** `forest.gif`, `wetland.gif`, `desert.gif`, `mountain.gif`

**Region ambience:** `ambient-forest.mp3`, `ambient-wetland.mp3`, `ambient-desert.mp3`, `ambient-mountain.mp3`

**Music and sound effects** (all optional, see below): `storyline_beginning.mp3`, `happyending_song.mp3`, `click.mp3`, `Victory.m4a`, `Congratulation.mp3`, `game over.mp3`, `correct answer.wav`, `Slash.m4a`, `sword smash .wav`, `Attacking.m4a`, `Monster laugh.m4a`, `Surprised.m4a`, `Relieved or tired.m4a`, `Heavy breathing.m4a`, `Laugh.m4a`, `Crying.m4a`, `Amazed.m4a`, `footstep.mp3`

If a sound file is missing the game keeps running and prints a warning in the browser console (F12). The click, slash and impact sounds fall back to built-in synthesized sounds. Missing images show as broken images or alt text, so check the console and the Network tab if something looks blank.

Browsers block audio until you click once, so music starts after the first click on the title screen.

## Customizing

**Questions** live in the `REGIONS` array in `script.js`:

```js
{ q: "What is the capital of France?", answer: "PARIS", difficulty: "easy" }
```

- `answer` is compared in capital letters with spaces and punctuation removed, so `"Mariana Trench"` and `"MARIANATRENCH"` both work.
- `difficulty` must be `"easy"`, `"medium"` or `"hard"`.
- Questions are drawn at random without repeats until the pool runs out. Each region currently has 6 to 9 questions, so add more for longer play.

**Balance:** `DAMAGE_BY_DIFFICULTY`, `BOSS_ATTACK_DAMAGE` and `QUESTION_TIME_LIMIT` are at the top of `script.js`.

**Story text:** `INTRO_SLIDES`, `ENDING_SLIDES`, and each region's `storyIntro` / `storyOutro` in `script.js`.

**Colors and animation speed:** CSS variables at the top of `style.css`.

## Known limitations

- Exit only shows a thank-you message, since browsers don't allow a page to close itself.
- Only region progress is saved (see Save system).
- Layout has been tested for flow and errors in a desktop browser. Check it on a phone before sharing.
