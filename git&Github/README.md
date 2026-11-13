# Git aur GitHub: Beginners Guide (Roman Urdu)

> **Note:** Is lecture mein hum zero se shuru karenge: Git kya hai, GitHub kya hai, Local aur Remote ka farq, file ki states (Untracked, Modified, Staged, Committed) aur har command ka matlab. Har command ke sath uska maqsad (kyun use hota hai) bhi likha hai.

---

## Lecture Roadmap

| Step | Topic | Maqsad |
| --- | --- | --- |
| 1 | Git kya hai aur kyun use karte hain? | Concept samajhna |
| 2 | GitHub kya hai? Git aur GitHub mein farq | Dono ka farq jaanna |
| 3 | Local aur Remote | Computer aur Internet ki copy samajhna |
| 4 | Git ke 3 areas | Working Directory, Staging, Repository |
| 5 | File ki States | Untracked, Modified, Staged, Committed |
| 6 | Git Setup | Installation aur configuration |
| 7 | Basic Git Commands | `init`, `status`, `add`, `commit`, `log`, `diff`, `restore` |
| 8 | GitHub Commands | `remote`, `push`, `pull`, `clone`, `fetch` |
| 9 | Branches | Alag raaste par kaam karna |
| 10 | `.gitignore` | Kuch files ko Git se door rakhna |
| 11 | Complete Workflow | Zero se GitHub tak ek project |
| 12 | Aam Errors aur Hal | Masail ka solution |
| 13 | Practice Questions | Khud karke seekhna |

---

## Step 1: Git kya hai?

### Pehle ek masla samjhein

Aap ek assignment bana rahi hain aur uski files ke naam aise ho jate hain:

```text
assignment.docx
assignment_final.docx
assignment_final_2.docx
assignment_final_REAL.docx
assignment_final_REAL_this_one.docx
```

Kaun si file sahi hai? Kal wali kaun si thi? Kisne kya change kiya? Yeh sab yaad rakhna mushkil hai.

### Git ka hal

**Git** ek **Version Control System (VCS)** hai. Yeh aap ke project ki **har tabdeeli (change) ka record** rakhta hai, taake aap:

- Kisi bhi purane version par **wapas ja sakein**.
- Dekh sakein ke **kisne, kab, kya** change kiya.
- Bohat se log **ek hi project par mil kar** kaam kar sakein.

### Real life example

> Game khelte waqt aap **save points** banate hain. Agar aage jaa kar game haar jayein, to pichle save point se dobara shuru kar sakte hain.
>
> Git bhi aap ke code ke **save points** banata hai. Har save point ko **commit** kehte hain.

### Git kyun use karte hain?

| Fayda | Matlab |
| --- | --- |
| **History** | Har change ka record, tareekh aur naam ke sath |
| **Undo** | Ghalti ho jaye to purane version par wapas jana |
| **Backup** | Code kho jaye to wapas mil jata hai (GitHub ke sath) |
| **Teamwork** | Kayi log ek project par bina ek doosre ka kaam mitaye kaam karte hain |
| **Experiment** | Naya feature alag **branch** mein try karein, main code safe rahe |
| **Professional skill** | Har software company Git use karti hai |

**Yaad rakhein:** Git ek **tool (software)** hai jo aap ke computer par chalta hai. Isay chalane ke liye internet ki zaroorat nahi.

---

## Step 2: GitHub kya hai?

**GitHub** ek **website (online platform)** hai jahan aap apne Git projects **internet par store** kar sakti hain.

### Real life example

> Git = aap ki **diary** jo aap ke ghar par hai.
> GitHub = ek **bank locker** jahan aap diary ki copy mehfooz (safe) rakhti hain, aur chahein to doosron ko bhi dikha sakti hain.

### Git aur GitHub mein farq

| | Git | GitHub |
| --- | --- | --- |
| Kya hai? | Software (tool) | Website (online service) |
| Kahan chalta hai? | Aap ke **computer** par | **Internet** par |
| Internet chahiye? | Nahi | Haan |
| Kaam | Changes ka record rakhna | Projects ko online store aur share karna |
| Kisne banaya? | Linus Torvalds (2005) | GitHub company (ab Microsoft ke under) |
| Misal | Camera jo photos kheenchta hai | Google Photos jahan photos upload hoti hain |

**Zaroori baat:** Git ke baghair GitHub nahi chal sakta, lekin Git GitHub ke baghair bhi chal sakta hai.

### GitHub kyun use karte hain?

- Code ka **online backup**.
- Dosto ya team ke sath **code share** karna.
- Ek project par **milkar kaam** karna.
- Apna **portfolio** (kaam ka showcase) banana, jo job interview mein dikhaya ja sakta hai.
- Doosron ke **open source** projects dekhna aur seekhna.

### GitHub ke ilawa bhi platforms hain

GitLab aur Bitbucket bhi isi tarah ke platforms hain. Commands sab par same hoti hain.

---

## Step 3: Local aur Remote

### Local kya hai?

**Local** ka matlab hai **aap ka apna computer**. Jo files aur Git history aap ke laptop par hai, woh **Local Repository** hai.

### Remote kya hai?

**Remote** ka matlab hai **internet par kisi aur jagah** rakhi hui copy, jaise GitHub ka server. Yeh **Remote Repository** hai.

### Real life example

| | Local | Remote |
| --- | --- | --- |
| Misal 1 | Aap ke phone ki gallery | Google Photos (cloud) |
| Misal 2 | Aap ke ghar ki diary | Bank locker mein rakhi copy |
| Misal 3 | Word file jo laptop par hai | Google Drive par upload ki hui file |

### Diagram

```
┌───────────────────────┐
│ Working Directory     │   (aap yahan files likhti hain)
└───────────────────────┘
        │
        │  git add
        ▼
┌───────────────────────┐
│ Staging Area          │   (commit ke liye files ka "tokra")
└───────────────────────┘
        │
        │  git commit
        ▼
┌───────────────────────┐
│ Local Repository      │   (aap ke computer par history)
└───────────────────────┘
        │          ▲
        │ git push │ git pull
        ▼          │
┌───────────────────────┐
│ Remote (GitHub)       │   (internet par copy)
└───────────────────────┘
```

**Diagram kaise parhein:** Pehle 3 boxes (Working Directory, Staging, Local Repository) aap ke **computer par** hain. Sab se neeche wala box **internet par** hai. `push` se local ka kaam upar (internet par) jata hai aur `pull` se wapas aata hai.

### Local aur Remote ka khulasa

| Command | Kaam | Direction |
| --- | --- | --- |
| `git push` | Local ka kaam GitHub par **bhejna** | Local ➜ Remote |
| `git pull` | GitHub ka naya kaam local par **lana** | Remote ➜ Local |
| `git clone` | GitHub ka poora project pehli baar local par **copy** karna | Remote ➜ Local |

---

## Step 4: Git ke 3 Areas

Git mein aap ki file **teen jagahon** se guzarti hai:

| Area | Matlab | Real life misal (parcel bhejna) |
| --- | --- | --- |
| **Working Directory** | Aap ka project folder jahan aap files banati aur edit karti hain | Aap ki mez jahan saman pada hai |
| **Staging Area** | Woh files jo aglay commit mein shamil hone wali hain | Saman jo aap ne **parcel box** mein rakh liya |
| **Repository** (`.git` folder) | Woh jagah jahan commits (save points) hamesha ke liye store hote hain | Parcel box **seal** karke label laga diya |

**Pura safar:**

1. Aap file banati hain ➜ **Working Directory**.
2. `git add` ➜ file **Staging Area** mein.
3. `git commit` ➜ file **Repository** mein permanently save.
4. `git push` ➜ GitHub (courier se bhej diya).

---

## Step 5: File ki States (Bohat Important)

Git ki nazar mein har file ki ek **state (halat)** hoti hai. `git status` command se yeh state pata chalti hai.

| State | Matlab | Real life misal |
| --- | --- | --- |
| **Untracked** | Nayi file, jise Git ne **abhi tak dekha hi nahi** | Naya mehman jis ka naam register mein nahi likha |
| **Modified** | Purani (tracked) file jis mein aap ne **change kar diya** lekin abhi staging mein nahi dala | Register mein likha hua naam jis mein aap ne correction ki |
| **Staged** | File **staging area** mein hai, aglay commit ke liye tayyar | Saman parcel box mein rakh diya |
| **Committed** | File ka change **repository mein save** ho chuka hai | Parcel seal ho gaya, record ban gaya |

**"Nothing" wali halat (Clean):** Jab saari files commit ho chuki hon aur koi nayi tabdeeli na ho, to `git status` yeh dikhata hai:

```text
nothing to commit, working tree clean
```

Iska matlab hai: "Koi kaam baqi nahi, sab kuch save hai."

### State ka Diagram (Lifecycle)

```
┌───────────┐  git add  ┌────────┐  git commit  ┌───────────┐
│ Untracked │ ────────► │ Staged │ ───────────► │ Committed │
└───────────┘           └────────┘              └───────────┘
                            ▲                        │
                            │ git add                │ file edit karein
                            │                        ▼
                            │                   ┌──────────┐
                            └───────────────────│ Modified │
                                                └──────────┘
```

**Diagram kaise parhein:**

- Nayi file **Untracked** hoti hai. `git add` se **Staged**, phir `git commit` se **Committed**.
- Committed file ko aap edit karein to woh **Modified** ho jati hai.
- Modified file ko dobara `git add` karein to phir **Staged** ho jati hai.

### `git status` ka output har state mein

**1. Untracked (nayi file `index.html` banayi):**

```text
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        index.html
```

**2. Staged (`git add index.html` ke baad):**

```text
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   index.html
```

**3. Committed / Clean (`git commit` ke baad):**

```text
nothing to commit, working tree clean
```

**4. Modified (committed file mein change kiya):**

```text
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
        modified:   index.html
```

### Yaad rakhne ka trick

| Output mein yeh likha ho | Matlab |
| --- | --- |
| `Untracked files` | Git ko file ka pata hi nahi |
| `Changes not staged for commit` | **Modified**: change hua, staging mein nahi gaya |
| `Changes to be committed` | **Staged**: commit ke liye tayyar |
| `nothing to commit, working tree clean` | **Clean**: sab kuch save hai |

---

## Step 6: Git Setup

### 1. Git install karna

Git ko [git-scm.com](https://git-scm.com) se download karke install karein. Windows par saath mein **Git Bash** (terminal) bhi install hota hai.

### 2. Check karna ke install hua ya nahi

```bash
git --version
```

**Output (example):**

```text
git version 2.43.0
```

### 3. Apna naam aur email set karna (sirf ek baar)

```bash
git config --global user.name "Ayesha Khan"
git config --global user.email "ayesha@example.com"
```

| Command | Kaam | Kyun zaroori hai? |
| --- | --- | --- |
| `git config --global user.name "..."` | Aap ka naam set karta hai | Har commit par yeh naam likha jata hai |
| `git config --global user.email "..."` | Aap ki email set karta hai | Commit ke sath email bhi save hoti hai |
| `git config --list` | Saari settings dikhata hai | Check karne ke liye ke settings sahi hain |

**Tip:** Wahi email use karein jo aap ke GitHub account par hai.

---

## Step 7: Basic Git Commands (Local Kaam)

Ab hum ek project par commands seekhte hain. Pehle terminal kholen aur project folder banayen.

### Command 1: `mkdir` aur `cd` (Terminal ki bunyadi commands)

```bash
mkdir my-project
cd my-project
```

| Command | Matlab |
| --- | --- |
| `mkdir my-project` | `my-project` naam ka naya folder banata hai |
| `cd my-project` | Us folder ke andar chala jata hai |

### Command 2: `git init`

```bash
git init
```

| | |
| --- | --- |
| **Kya karta hai?** | Folder mein ek chhupa hua `.git` folder bana deta hai, jis se woh folder **Git repository** ban jata hai |
| **Kyun use hota hai?** | Naye project mein Git ki tracking **shuru** karne ke liye |
| **Kab use karein?** | Sirf **ek baar**, project ke shuru mein |

**Output:**

```text
Initialized empty Git repository in .../my-project/.git/
```

**Dhyan dein:** `.git` folder ko kabhi delete na karein, is mein poori history hai.

### Command 3: `git status`

```bash
git status
```

| | |
| --- | --- |
| **Kya karta hai?** | Batata hai ke kaun si file **Untracked, Modified, Staged** hai ya sab **clean** hai |
| **Kyun use hota hai?** | Har step se pehle aur baad check karne ke liye ke abhi kya halat hai |
| **Kab use karein?** | Bar bar! Yeh sab se zyada use hone wali command hai |

**Tip:** Jab confuse hon, to `git status` chala lein. Yeh agla step bhi batata hai.

### Command 4: `git add`

Pehle ek file banayen (`index.html`), phir:

```bash
git add index.html
```

| | |
| --- | --- |
| **Kya karta hai?** | File ko **Staging Area** mein daalta hai |
| **Kyun use hota hai?** | Hum chuntay hain ke aglay commit mein **kaun si files** shamil hongi |
| **Real life** | Saman ko parcel box mein rakhna |

**`git add` ke different tareeqe:**

| Command | Kaam |
| --- | --- |
| `git add index.html` | Sirf ek khaas file stage karta hai |
| `git add index.html style.css` | Kayi files ek sath stage karta hai |
| `git add .` | Current folder ki **saari** nayi aur modified files stage karta hai |
| `git add -A` | Poore project ki **saari** tabdeeliyan stage karta hai (nayi, modified, deleted) |

### Command 5: `git commit`

```bash
git commit -m "Add homepage"
```

| | |
| --- | --- |
| **Kya karta hai?** | Staging Area ki files ka **save point (snapshot)** bana deta hai |
| **Kyun use hota hai?** | Apne kaam ka permanent record rakhne ke liye |
| **`-m` ka matlab** | **message**: yeh batata hai ke is commit mein kya kiya |
| **Real life** | Parcel box seal karke us par label lagana |

**Output (example):**

```text
[main (root-commit) a1b2c3d] Add homepage
 1 file changed, 1 insertion(+)
 create mode 100644 index.html
```

**Acha commit message kaisa hota hai?**

| Ghalat (mubham) | Sahi (wazeh) |
| --- | --- |
| `update` | `Add login page` |
| `changes` | `Fix spelling mistake in homepage` |
| `asdfgh` | `Add contact form` |

**Tip:** Message chhota, saaf, aur kaam batane wala ho. Shuru mein `Add`, `Fix`, `Update`, `Remove` jaise lafz use karein.

### Command 6: `git log`

```bash
git log
git log --oneline
```

| Command | Kaam |
| --- | --- |
| `git log` | Saare commits ki tafseel dikhata hai (commit ID, author, date, message) |
| `git log --oneline` | Har commit ek line mein dikhata hai (chhota aur saaf) |

| | |
| --- | --- |
| **Kyun use hota hai?** | Project ki **history** dekhne ke liye: kisne, kab, kya kiya |

**Output (`--oneline`):**

```text
c3d4e5f Add contact form
a1b2c3d Add homepage
```

**Tip:** `git log` se bahar niklne ke liye keyboard par **`q`** dabayein.

### Command 7: `git diff`

```bash
git diff
git diff --staged
```

| Command | Kaam |
| --- | --- |
| `git diff` | Woh changes dikhata hai jo abhi **staged nahi** hue (Modified) |
| `git diff --staged` | Woh changes dikhata hai jo **staged** ho chuke hain (commit se pehle) |

| | |
| --- | --- |
| **Kyun use hota hai?** | Commit karne se pehle **dekhne ke liye** ke exactly kya badla hai |

Output mein `-` (minus) wali line **hata di gayi** aur `+` (plus) wali line **add ki gayi** line hoti hai.

### Command 8: `git restore`

```bash
git restore index.html
git restore --staged index.html
```

| Command | Kaam | Kab use karein? |
| --- | --- | --- |
| `git restore index.html` | File ko **last commit wali halat** par wapas le jata hai (aap ke unsaved changes **mit jate hain**) | Jab aap ne ghalti se file kharab kar di |
| `git restore --staged index.html` | File ko **Staging Area se bahar** nikalta hai (file mein changes safe rehte hain) | Jab galat file `git add` ho gayi |

**Warning:** `git restore index.html` ke baad changes **wapas nahi aate**. Soch samajh kar chalayein.

### Command 9: `git rm` (file hatana)

```bash
git rm old-file.txt
```

| | |
| --- | --- |
| **Kya karta hai?** | File ko folder se bhi hata deta hai aur Git ko bhi bata deta hai ke yeh file ab project ka hissa nahi |
| **Phir kya karein?** | Is change ko bhi `git commit` karein |

### Basic Commands ka Khulasa

| Command | Aasan matlab |
| --- | --- |
| `git init` | Project mein Git shuru karo |
| `git status` | Abhi kya halat hai? |
| `git add` | Files ko parcel box (staging) mein rakho |
| `git commit -m "..."` | Box seal karo aur save point banao |
| `git log` | History dikhao |
| `git diff` | Kya badla hai dikhao |
| `git restore` | Ghalti wapas theek karo |

---

## Step 8: GitHub Commands (Remote Kaam)

### GitHub par repository banane ke steps

1. [github.com](https://github.com) par **account** banayen.
2. Upar **`+`** par click karke **New repository** chunein.
3. **Repository name** likhein (jaise `my-project`).
4. **Public** (sab dekh sakte hain) ya **Private** (sirf aap) chunein.
5. Agar aap ka project pehle se computer par hai, to **README, .gitignore ya license add na karein**, khali repository banayen.
6. **Create repository** dabayen.
7. Page par ek **URL** milega, jaise `https://github.com/ayesha/my-project.git`. Isay copy kar lein.

### Command 1: `git remote add origin`

```bash
git remote add origin https://github.com/ayesha/my-project.git
```

| Hissa | Matlab |
| --- | --- |
| `git remote add` | Ek remote (online jagah) jodo |
| `origin` | Us remote ka **naam** (aam taur par `origin` hi rakhte hain) |
| `https://...` | GitHub repository ka **URL** |

| | |
| --- | --- |
| **Kya karta hai?** | Aap ke local project ko GitHub ki repository se **jorta** hai |
| **Kyun use hota hai?** | Taake Git ko pata ho ke `push` karte waqt code kahan bhejna hai |
| **Kab use karein?** | Sirf **ek baar** (jab local project pehle se bana ho) |

**Real life:** Phone mein kisi ka number **save** karna. Ab aap us ko call (push) kar sakti hain.

### Command 2: `git remote -v`

```bash
git remote -v
```

| | |
| --- | --- |
| **Kya karta hai?** | Jore hue remotes ki list aur unke URLs dikhata hai |
| **Kyun use hota hai?** | Check karne ke liye ke remote sahi jora hai |

**Output:**

```text
origin  https://github.com/ayesha/my-project.git (fetch)
origin  https://github.com/ayesha/my-project.git (push)
```

### Command 3: `git branch -M main`

```bash
git branch -M main
```

| | |
| --- | --- |
| **Kya karta hai?** | Current branch ka naam **`main`** kar deta hai |
| **Kyun use hota hai?** | Kuch purane Git versions mein default branch ka naam `master` hota hai, jabke GitHub `main` use karta hai |

### Command 4: `git push`

```bash
git push -u origin main
```

| Hissa | Matlab |
| --- | --- |
| `git push` | Local commits ko remote par **bhejo** |
| `origin` | Kahan bhejna hai (GitHub) |
| `main` | Kaun si branch bhejni hai |
| `-u` | Is branch ko origin ke sath **hamesha ke liye jor do** |

| | |
| --- | --- |
| **Kya karta hai?** | Aap ke **commits** ko GitHub par upload karta hai |
| **Kyun use hota hai?** | Online backup banane aur doosron ke sath share karne ke liye |

**Pehli dafa** `git push -u origin main` likhein. Uske baad sirf:

```bash
git push
```

**Dhyan dein:** `push` sirf **committed** kaam bhejta hai. Agar aap ne commit nahi kiya, to GitHub par kuch nahi jayega.

**Login ke bare mein:**

- GitHub ab HTTPS ke zariye **password** qabool nahi karta. Terminal par pehli dafa push karne par browser login window aa sakti hai (Git Credential Manager ke zariye) ya **Personal Access Token** maanga ja sakta hai.
- Agar masla aaye to **GitHub Desktop** ya **VS Code** ke zariye sign in karna sab se asaan hai.

### Command 5: `git clone`

```bash
git clone https://github.com/ayesha/my-project.git
```

| | |
| --- | --- |
| **Kya karta hai?** | GitHub ke poore project ki **copy** aap ke computer par bana deta hai (history ke sath), aur remote `origin` bhi khud jor deta hai |
| **Kyun use hota hai?** | Kisi aur ka (ya apna) project pehli baar computer par laane ke liye |
| **Kab use karein?** | Jab project computer par **maujood na ho** |

**Farq yaad rakhein:**

| Halat | Command |
| --- | --- |
| Project pehle se computer par hai, GitHub par bhejna hai | `git remote add origin ...` phir `git push` |
| Project GitHub par hai, computer par laana hai | `git clone ...` |

### Command 6: `git pull`

```bash
git pull
```

| | |
| --- | --- |
| **Kya karta hai?** | GitHub par jo **naye changes** hain unhein download karke aap ke local project mein **mila deta hai** |
| **Kyun use hota hai?** | Doosre team members ka kaam lene ke liye, ya doosre computer par kiya hua kaam lene ke liye |
| **Kab use karein?** | Kaam **shuru karne se pehle**, aur `push` karne se pehle |

### Command 7: `git fetch`

```bash
git fetch
```

| | |
| --- | --- |
| **Kya karta hai?** | GitHub ke naye changes **download** karta hai lekin aap ke kaam mein **mix nahi karta** |
| **Kyun use hota hai?** | Pehle dekhne ke liye ke remote par kya naya aaya hai |

**Farq:**

| Command | Download karta hai? | Mix (merge) karta hai? |
| --- | --- | --- |
| `git fetch` | Haan | **Nahi** |
| `git pull` | Haan | **Haan** (`fetch` + `merge`) |

### GitHub Commands ka Khulasa

| Command | Aasan matlab |
| --- | --- |
| `git remote add origin URL` | Local project ko GitHub se jodo |
| `git remote -v` | Jora hua remote check karo |
| `git branch -M main` | Branch ka naam `main` rakho |
| `git push -u origin main` | Pehli dafa code GitHub par bhejo |
| `git push` | Baad mein naya kaam bhejo |
| `git pull` | GitHub se naya kaam lao |
| `git clone URL` | GitHub ka project computer par copy karo |
| `git fetch` | Naya kaam download karo, mix mat karo |

---

## Step 9: Branches (Alag Raaste)

### Branch kya hai?

**Branch** aap ke project ka ek **alag raasta (parallel version)** hai. Aap us par naya kaam karti hain bina **main** code ko kharab kiye.

**Real life example:** Aap ek kitab likh rahi hain. Ek naya chapter try karna hai, lekin pata nahi achha lagega ya nahi. Aap kitab ki **photocopy** par chapter likhti hain. Pasand aaye to asli kitab mein jod dein, warna photocopy phenk dein.

### Diagram

```
 main     ●───●───●───────────────●───●
                   \             /
 feature            ●───●───●───●
                (naya kaam)    (merge)
```

### Branch ki Commands

| Command | Kaam |
| --- | --- |
| `git branch` | Saari branches ki list dikhata hai (current branch par `*` hota hai) |
| `git branch feature-login` | `feature-login` naam ki naye branch banata hai |
| `git switch feature-login` | `feature-login` branch par chala jata hai |
| `git switch -c feature-login` | Nayi branch **banata bhi hai aur us par chala bhi jata hai** |
| `git switch main` | Wapas `main` branch par aa jata hai |
| `git merge feature-login` | `feature-login` ka kaam **current branch mein mila deta hai** |
| `git branch -d feature-login` | Merge ke baad branch delete karta hai |

### Example: Naya feature banana

```bash
git switch -c feature-contact     # nayi branch banao aur us par jao
# ... files mein kaam karein ...
git add .
git commit -m "Add contact page"
git switch main                   # wapas main par
git merge feature-contact         # kaam main mein mila do
git push                          # GitHub par bhej do
```

---

## Step 10: `.gitignore`

### Kya hai?

`.gitignore` ek khaas file hai jis mein aap un files ke naam likhti hain jinhein Git ko **nazar-andaaz (ignore)** karna hai.

### Kyun use hota hai?

Kuch files GitHub par nahi jani chahiye:

| File | Wajah |
| --- | --- |
| Passwords aur secret keys (`.env`) | Security: doosre dekh sakte hain |
| `node_modules/` folder | Bohat bara hota hai aur dobara ban sakta hai |
| `*.log` files | Faltu aur temporary |

### Example

Project folder mein `.gitignore` naam ki file banayen aur is mein likhein:

```text
.env
node_modules/
*.log
```

| Line | Matlab |
| --- | --- |
| `.env` | `.env` file ignore karo |
| `node_modules/` | Poora `node_modules` folder ignore karo |
| `*.log` | Har woh file ignore karo jis ka naam `.log` par khatam ho |

**Tip:** `.gitignore` ko khud `git add` aur `git commit` karna chahiye.

---

## Step 11: Complete Workflow (Zero se GitHub tak)

### Scenario A: Naya project computer par, phir GitHub par bhejna

```bash
# 1. Folder banao aur andar jao
mkdir my-first-project
cd my-first-project

# 2. Git shuru karo
git init

# 3. Ek file banao (README.md) aur uska content likho
echo "# My First Project" > README.md

# 4. Halat dekho (README.md Untracked hogi)
git status

# 5. File ko staging mein daalo
git add README.md

# 6. Halat dekho (README.md Staged hogi)
git status

# 7. Save point banao
git commit -m "Add README"

# 8. Halat dekho (working tree clean)
git status

# 9. GitHub se jodo (apna URL likhein)
git remote add origin https://github.com/YOUR-USERNAME/my-first-project.git

# 10. Branch ka naam main karo
git branch -M main

# 11. GitHub par bhejo
git push -u origin main
```

**Result:** GitHub par repository kholein aur page refresh karein. Aap ki `README.md` file nazar aa jayegi.

### Scenario B: Project pehle se GitHub par hai

```bash
git clone https://github.com/YOUR-USERNAME/my-first-project.git
cd my-first-project
```

### Roz ka Kaam (Daily Workflow)

```
┌─────────────────────────────┐
│ 1. git pull                 │   Naya kaam lao
└─────────────────────────────┘
              │
              ▼
┌─────────────────────────────┐
│ 2. Files mein kaam karein   │
└─────────────────────────────┘
              │
              ▼
┌─────────────────────────────┐
│ 3. git status               │   Kya badla, check karo
└─────────────────────────────┘
              │
              ▼
┌─────────────────────────────┐
│ 4. git add .                │   Staging mein daalo
└─────────────────────────────┘
              │
              ▼
┌─────────────────────────────┐
│ 5. git commit -m "..."      │   Save point banao
└─────────────────────────────┘
              │
              ▼
┌─────────────────────────────┐
│ 6. git push                 │   GitHub par bhejo
└─────────────────────────────┘
```

---

## Step 12: Aam Errors aur Unka Hal

| Error / Message | Wajah | Hal |
| --- | --- | --- |
| `fatal: not a git repository` | Aap us folder mein hain jahan `git init` nahi hua | Sahi folder mein `cd` karein, ya `git init` chalayein |
| `nothing to commit, working tree clean` | Koi nayi tabdeeli nahi hai | Yeh error nahi, bas info hai. File edit karein phir commit karein |
| `Author identity unknown` | Naam aur email set nahi hain | `git config --global user.name` aur `user.email` chalayein |
| `pathspec '...' did not match any files` | File ka naam ghalat likha ya file maujood nahi | `ls` (ya `dir`) se sahi naam check karein |
| `remote origin already exists` | `origin` pehle se jora hua hai | `git remote -v` se check karein. Badalna ho to `git remote set-url origin NEW-URL` |
| `failed to push some refs` | GitHub par aisa naya kaam hai jo aap ke paas nahi | Pehle `git pull`, phir `git push` |
| `Authentication failed` | Login ya token ghalat | Dobara login karein ya Personal Access Token use karein |
| `src refspec main does not match any` | Abhi tak koi commit nahi hua | Pehle kam az kam ek `git commit` karein |

---

## Final Revision

| Concept | Yaad rakhein |
| --- | --- |
| Git | Software jo aap ke code ki history (save points) rakhta hai |
| GitHub | Website jahan Git projects online store hote hain |
| Local | Aap ka computer |
| Remote | Internet par copy (GitHub) |
| Untracked | Nayi file, Git ko pata nahi |
| Modified | Purani file mein change, staging mein nahi |
| Staged | Commit ke liye tayyar |
| Committed (Clean) | Save ho chuki, `nothing to commit` |
| `git init` | Project mein Git shuru |
| `git add` | Staging mein daalo |
| `git commit -m` | Save point banao |
| `git push` | Local se GitHub par bhejo |
| `git pull` | GitHub se local par lao |
| `git clone` | GitHub project ki pehli copy computer par |
| Roz ka rasta | `pull` ➜ kaam ➜ `status` ➜ `add` ➜ `commit` ➜ `push` |

---

## Step 13: Practice Questions (Students ke liye)

### Section A: Concept Questions

**Question 1: Git ya GitHub?**

- **Scenario:** Neeche di gayi har baat ke samne likhein ke woh **Git** ke bare mein hai ya **GitHub** ke bare mein.
- **Task:** Table complete karein.

| Baat | Git ya GitHub? |
| --- | --- |
| Yeh aap ke computer par install hota hai | ? |
| Yeh ek website hai jahan projects online rakhe jate hain | ? |
| Yeh internet ke baghair bhi chal sakta hai | ? |
| Is par aap apna portfolio dikha sakti hain | ? |

- **Expected Answer:** Git, GitHub, Git, GitHub.

**Question 2: Local ya Remote?**

- **Scenario:** Hira ke laptop par ek folder hai jis mein uska project hai, aur GitHub par bhi uski ek copy hai.
- **Task:** Batayein ke laptop wali copy **Local** hai ya **Remote**, aur GitHub wali copy kya hai.
- **Expected Answer:** Laptop wali copy **Local**, GitHub wali copy **Remote**.

### Section B: File State Questions

**Question 3: State pehchanein**

- **Scenario:** Sana ne `notes.txt` naam ki nayi file banayi hai. Neeche har step ke baad batayein ke file ki state kya hogi.
- **Task:** Table complete karein.

| Step | File ki state |
| --- | --- |
| 1. Sana ne `notes.txt` banayi | ? |
| 2. `git add notes.txt` chalaya | ? |
| 3. `git commit -m "Add notes"` chalaya | ? |
| 4. `notes.txt` mein ek nayi line likhi | ? |
| 5. `git add notes.txt` dobara chalaya | ? |

- **Expected Answer:** 1. Untracked, 2. Staged, 3. Committed (clean), 4. Modified, 5. Staged.

**Question 4: `git status` ka output**

- **Scenario:** Maryam ne `git status` chalaya aur yeh output aaya:

```text
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
        modified:   index.html
```

- **Task:** Batayein ke `index.html` ki state kya hai, aur usay commit karne ke liye kaun si 2 commands chalani hongi.
- **Expected Answer:** State **Modified** hai. Commands: `git add index.html` aur phir `git commit -m "Update homepage"`.

### Section C: Command Questions

**Question 5: Sahi command chunein**

- **Task:** Har situation ke samne sahi command likhein.

| Situation | Command |
| --- | --- |
| Naye folder mein Git shuru karna | ? |
| Dekhna ke kaun si files modified hain | ? |
| `index.html` ko staging mein daalna | ? |
| Staging ki files ka save point banana, message "Add homepage" | ? |
| Commits ki history ek line mein dekhna | ? |
| Local commits GitHub par bhejna | ? |
| GitHub ka naya kaam local par lana | ? |
| GitHub ka project pehli baar computer par copy karna | ? |

- **Expected Answer:** `git init`, `git status`, `git add index.html`, `git commit -m "Add homepage"`, `git log --oneline`, `git push`, `git pull`, `git clone URL`.

**Question 6: Ghalti theek karein**

- **Scenario:** Noor ne ghalti se `secret.txt` ko `git add` kar diya, lekin woh isay commit nahi karna chahti.
- **Task:** Kaun si command se `secret.txt` staging se bahar niklegi (file ke changes safe rehne chahiye)?
- **Expected Answer:** `git restore --staged secret.txt`

**Question 7: `push` kyun nahi hua?**

- **Scenario:** Areeba ne `index.html` mein change kiya aur seedha `git push` chalaya, lekin GitHub par change nazar nahi aaya.
- **Task:** Ghalti kya thi aur sahi order kya hona chahiye?
- **Expected Answer:** Areeba ne `git add` aur `git commit` nahi kiya. Sahi order: `git add .` ➜ `git commit -m "Update index.html"` ➜ `git push`.

### Section D: Practical Lab Tasks (Computer par karke dekhein)

**Lab 1: Pehla Local Repository**

- **Scenario:** Aap ko ek naya project `my-first-project` shuru karna hai.
- **Task:**
  1. `my-first-project` folder banayen aur us mein jayen.
  2. `git init` chalayen.
  3. `README.md` file banayen jis mein `# My First Project` likha ho.
  4. `git status` chalayen aur dekhen file ki state.
  5. `git add README.md` aur `git commit -m "Add README"` chalayen.
  6. Dobara `git status` chalayen.
- **Expected Result:** Step 4 mein `Untracked files`, aur step 6 mein `nothing to commit, working tree clean` nazar aana chahiye.

**Lab 2: GitHub par bhejna**

- **Scenario:** Lab 1 ka project ab GitHub par bhejna hai.
- **Task:**
  1. GitHub par khali repository `my-first-project` banayen.
  2. Terminal mein `git remote add origin URL` chalayen.
  3. `git branch -M main` chalayen.
  4. `git push -u origin main` chalayen.
  5. GitHub page refresh karein.
- **Expected Result:** GitHub par `README.md` file nazar aaye.

**Lab 3: Change aur dobara push**

- **Scenario:** README mein ek nayi line likhni hai.
- **Task:**
  1. `README.md` mein ek nayi line likhen.
  2. `git status` chalayen (state kya hai?).
  3. `git diff` chalayen (kya badla?).
  4. `git add .`, `git commit -m "Update README"`, `git push` chalayen.
  5. `git log --oneline` chalayen.
- **Expected Result:** Step 2 mein `modified: README.md`, step 3 mein `+` wali nayi line, aur step 5 mein **2 commits** nazar aane chahiyen.

**Lab 4: Clone**

- **Scenario:** Aap ke paas dusra computer (ya dusra folder) hai aur wahan project laana hai.
- **Task:**
  1. Naye folder mein terminal kholen.
  2. `git clone URL` chalayen.
  3. Clone hue folder mein ja kar `git log --oneline` chalayen.
- **Expected Result:** Poora project aur dono commits wahan maujood hon.

---

## Teacher Answer Key (Summary)

| Question | Answer |
| --- | --- |
| Q1 | Git, GitHub, Git, GitHub |
| Q2 | Laptop = Local, GitHub = Remote |
| Q3 | Untracked, Staged, Committed (clean), Modified, Staged |
| Q4 | Modified. `git add index.html` phir `git commit -m "..."` |
| Q5 | `git init`, `git status`, `git add index.html`, `git commit -m "Add homepage"`, `git log --oneline`, `git push`, `git pull`, `git clone URL` |
| Q6 | `git restore --staged secret.txt` |
| Q7 | `add` aur `commit` nahi kiya. Sahi order: `add` ➜ `commit` ➜ `push` |
| Lab 1 | Step 4: `Untracked files`. Step 6: `nothing to commit, working tree clean` |
| Lab 2 | GitHub par `README.md` nazar aaye |
| Lab 3 | `modified: README.md`, diff mein `+` line, log mein 2 commits |
| Lab 4 | Poora project aur 2 commits clone folder mein maujood |