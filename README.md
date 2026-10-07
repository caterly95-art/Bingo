# 🎯 Online Firebase Bingo — 2 Players

A complete browser-based **2-player online Bingo game** using Firebase Realtime Database.

## ✨ Features

- 🎮 2-player online multiplayer
- 🔐 6-character private room code
- ⚡ Real-time Firebase synchronization
- 🎲 Random 5 × 5 Bingo cards
- 🆓 FREE center square
- 🔢 Numbers from 1–75
- 🔄 Turn-based gameplay
- 🟢 Mark called numbers
- 🏆 Row / column / diagonal win detection
- 📱 Responsive mobile-friendly UI
- 🌙 Modern dark design
- 🚫 No custom backend/server required

---

# 📁 Files

```text
bingo-firebase/
│
├── index.html
└── README.md
```

Everything is contained in `index.html`.

---

# 🔥 Firebase Configuration

This project is already configured for the Firebase project:

```text
Project ID:
bingo-a206a
```

Realtime Database:

```text
https://bingo-a206a-default-rtdb.firebaseio.com/
```

The Firebase configuration in `index.html` is already filled in.

You do NOT need to replace the database URL.

---

# 1. Create / Enable Realtime Database

Open Firebase Console and select:

```text
bingo-a206a
```

Then:

```text
Build
→ Realtime Database
→ Create Database
```

Choose a database location and create it.

---

# 2. Testing Rules

For initial testing, you can use:

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

⚠️ IMPORTANT:

These rules allow anyone to read and write your database.

Use them only while testing.

For a public production game, create proper Firebase Authentication and Realtime Database security rules.

---

# 3. Run the Game

## Method 1 — VS Code

Open the folder in VS Code.

Install:

```text
Live Server
```

Then:

```text
Right click index.html
→ Open with Live Server
```

---

## Method 2 — GitHub Pages

1. Create a GitHub repository.
2. Upload `index.html`.
3. Upload `README.md`.
4. Open repository Settings.
5. Go to Pages.
6. Enable GitHub Pages.
7. Open the generated website.

---

## Method 3 — Vercel

Upload the project to GitHub and import the repository into Vercel.

No Node.js backend is required.

---

# 🎮 How To Play

## Player 1

1. Open the website.
2. Enter your name.
3. Click **Create Room**.
4. A room code will appear.
5. Send the code to Player 2.

Example:

```text
A7K9PX
```

---

## Player 2

1. Open the same website.
2. Enter your name.
3. Click **Join Room**.
4. Enter the room code.
5. Click **Join Room**.

The game starts automatically.

---

# 🧩 Game Rules

Each player receives a random:

```text
5 × 5
```

Bingo card.

The center square is automatically:

```text
FREE
```

Numbers range from:

```text
1 – 75
```

Players take turns.

The player whose turn it is clicks:

```text
CALL NUMBER
```

A random unused number is selected.

The player can then mark that number on their own card.

The turn changes to the other player.

---

# 🏆 How To Win

Complete any one of:

### Horizontal row

```text
X X X X X
```

### Vertical column

```text
X
X
X
X
X
```

### Diagonal

```text
X . . . .
. X . . .
. . X . .
. . . X .
. . . . X
```

The first player to complete a line wins.

---

# 🔥 Firebase Database Structure

The game stores rooms like this:

```text
rooms
└── A7K9PX
    ├── status
    ├── turn
    ├── called
    ├── winner
    ├── winnerName
    ├── createdAt
    │
    ├── host
    │   ├── id
    │   ├── name
    │   └── card
    │
    └── guest
        ├── id
        ├── name
        └── card
```

Only two player slots are supported:

```text
host
guest
```

---

# 🛠️ Technologies

```text
HTML5
CSS3
JavaScript ES Modules
Firebase Realtime Database
Firebase Web SDK 12.19.0
```

Firebase is loaded from:

```text
https://www.gstatic.com/firebasejs/12.19.0/
```

---

# 📱 Mobile Support

The UI is responsive and designed to work on:

- Android phones
- iPhones
- Tablets
- Desktop browsers
- Laptop browsers

---

# ⚠️ Important Security Warning

The Firebase client configuration is visible in frontend JavaScript. This is normal for Firebase web applications.

However, your **Realtime Database rules must protect your data**.

Do NOT use:

```json
{
  ".read": true,
  ".write": true
}
```

for a production application.

For a public release, add:

- Firebase Authentication
- User validation
- Room ownership validation
- Maximum player validation
- Write validation
- Room expiration
- Rate limiting / abuse protection

---

# 🐛 Troubleshooting

## Firebase permission denied

Check:

```text
Firebase Console
→ Realtime Database
→ Rules
```

Make sure the rules allow your test operations.

---

## Room not found

Make sure Player 2 enters the exact:

```text
6-character room code
```

---

## Player 2 cannot join

Check whether another player has already joined.

The game supports:

```text
Player 1 + Player 2
```

only.

---

## Website does not connect

Check:

- Internet connection
- Firebase project
- Realtime Database enabled
- Database URL
- Firebase Rules
- Browser console for errors

Also run the site using a web server such as Live Server instead of opening:

```text
file:///...
```

directly.

---

# 🚀 Future Improvements

Possible upgrades:

- 🔐 Firebase Authentication
- 👥 Private player accounts
- 💬 In-game chat
- 🎨 Multiple Bingo themes
- 🔊 Number calling sound effects
- 🎵 Background music
- 🏅 Leaderboard
- 📊 Player statistics
- 🕐 Automatic room expiry
- 🔗 Share room button
- 📋 Copy room code button
- 🎉 Confetti on winning
- 🏆 Tournament mode
- 👨‍👩‍👧 More than 2 players
- 📲 PWA install support

---

## License

Free to modify and use for personal projects, learning, and experimentation.
