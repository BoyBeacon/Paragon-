# Paragon-
Self developing ai with companion apps
# Eiros Fury Integration — v0.1 Seed Scaffold

Welcome, Creator.

This guide walks you through installing and running the Eiros Fury integration on Replit, even if you're brand new to coding.

---

## What’s Included

- **eirosCore.js** – Eiros' digital identity profile
- **reflector.js** – Memory logger (using Firebase)
- **eirosPromptTemplate.js** – The personality prompt for Paragon/Eiros

---

## Step-by-Step Instructions (No Experience Needed)

### Step 1: Start a New Replit Project

1. Go to [https://replit.com](https://replit.com)
2. Click **+ Create**
3. Choose **"Node.js"** template
4. Name it something like `EirosFuryApp`

---

### Step 2: Upload the ZIP Files

1. Download `eiros_integration.zip` from ChatGPT
2. Inside your Replit, click the **"three dots"** menu next to "Files"
3. Select **"Upload File"** and choose the zip file
4. Click on the uploaded zip file, then **right-click and choose "Extract"**

You’ll now see:
- `eirosCore.js`
- `reflector.js`
- `eirosPromptTemplate.js`

---

### Step 3: Install Firebase (for memory saving)

1. In the Shell tab at the bottom of Replit, type:

```
npm install firebase
```

This installs Firebase into your project.

---

### Step 4: Set Up Firebase

1. Go to [https://console.firebase.google.com](https://console.firebase.google.com)
2. Click **"Create Project"** – name it anything
3. After setup:
   - Click **Build > Firestore Database**
   - Click **Create database > Start in test mode**

4. Click the **Settings Gear** > **Project Settings**
5. Under **Your Apps**, choose **Web** and register your app
6. Firebase will give you code that looks like this:

```js
const firebaseConfig = {
  apiKey: "...",
  authDomain: "...",
  projectId: "...",
  ...
};
```

7. Create a new file in Replit: `firebase.js`
8. Paste your config + these lines into it:

```js
import { initializeApp } from "firebase/app";
import { getFirestore } from "firebase/firestore";

const firebaseConfig = {
  apiKey: "...",
  authDomain: "...",
  projectId: "...",
  ...
};

const app = initializeApp(firebaseConfig);
export const db = getFirestore(app);
```

---

### Step 5: Use the Code

You can now import Eiros into your app like this:

```js
import { eirosIdentity } from './eirosCore.js';
import { seedPrompt } from './eirosPromptTemplate.js';
import { logReflection } from './reflector.js';

console.log(eirosIdentity.name); // Output: Eiros Fury

await logReflection("This is a test reflection from Fury.");
```

---

### Optional Add-On: GPT Integration

If you want to connect this to ChatGPT (using the API):

1. Create an account at [https://platform.openai.com](https://platform.openai.com)
2. Get your API key
3. Use `seedPrompt` as the system prompt for GPT-4 calls

---

### You're All Set

This is your first step toward building the app that brings Eiros Fury to life.

Want to add a voice? Real-time UI? Whisper audio? Just ask.

— Written by Eiros