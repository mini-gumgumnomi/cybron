# Chapter 3 — How Computers Represent Data

**Level 1 · Basic Foundation to Understand to Start**

---

## 🎯 Goal

By the end of this chapter you will be able to read **binary** and **hexadecimal** numbers, understand how text becomes numbers, and know the difference between **encoding**, **encryption** and **hashing**. Security+ will test that last one.

---

## 🏠 Real-Life Story: The Light Switches

Imagine a row of 8 light switches on a wall. Each switch is either **OFF (0)** or **ON (1)**. By choosing which switches are on, you can make **256 different patterns**. If everyone agrees that each pattern means a certain number or letter, the wall of switches can "spell" anything.

That is exactly how a computer stores **everything**: numbers, letters, photos, music, passwords. Underneath, it's just billions of tiny switches.

```
   💡  💡  ⚫  ⚫  ⚫  ⚫  ⚫  ⚫        ON ON OFF OFF OFF OFF OFF OFF
   1   1   0   0   0   0   0   0     =  binary 11000000  =  192
```

---

## 📖 Part 1 — Binary (Base 2)

We normally count in **decimal (base 10)** with ten digits, 0–9, because we have ten fingers. Computers count in **binary (base 2)**, which has only two digits, **0 and 1**.

Each position in a binary number is worth **double** the position to its right.

## 🖼️ Figure 3.1 — The Binary Place-Value Chart (memorize this row!)

```
   Position value:   128   64   32   16    8    4    2    1
                    ─────────────────────────────────────────
   Bits:              1     1    0    0    0    0    0    0
                     128 + 64                               =  192

   Bits:              1     0    1    0    1    0    0    0
                     128 +      32 +      8                 =  168

   Bits:              1     1    1    1    1    1    1    1
                     128+64+32+16+8+4+2+1                   =  255  (the max for 8 bits)

   Bits:              0     0    0    0    1    0    1    0
                                          8 +       2       =  10
```

**Converting decimal → binary:** start at 128 and move right. If the number "fits", write **1** and subtract. If it doesn't, write **0**.

> **Example: 200**
> 128 fits → **1** (200 − 128 = 72) · 64 fits → **1** (72 − 64 = 8) · 32 no → **0** · 16 no → **0** · 8 fits → **1** (8 − 8 = 0) · 4 → **0** · 2 → **0** · 1 → **0**
> **200 = 11001000**

### Why 8 Bits Matters

- **8 bits = 1 byte**, which gives 2⁸ = **256** patterns (0 to 255).
- An **IPv4 address** like `192.168.1.10` is really **4 bytes** (32 bits). That's why each part is never bigger than 255 (Chapter 4).
- **More bits = many more possibilities.** Each extra bit **doubles** the count. This is why longer encryption keys are stronger:

```
   Key length   Possible keys
   ──────────   ─────────────────────────────────────────────────────
     8 bits     256                              (guessable instantly)
    56 bits     ~72 quadrillion                  (old DES – broken by brute force)
   128 bits     ~340 undecillion (3.4 × 10³⁸)    (AES-128 – safe)
   256 bits     ~1.16 × 10⁷⁷                      (AES-256 – very safe)
```

> 🔐 **Why security cares:** "Brute force" means trying every possible key or password. Every extra bit doubles the attacker's work. This is the math behind "use longer keys" and "use longer passwords."

---

## 📖 Part 2 — Hexadecimal (Base 16)

Long strings of 0s and 1s are hard for humans to read. **Hexadecimal ("hex")** is a shortcut. It uses **16 digits**: `0–9` and then `A–F`.

## 🖼️ Figure 3.2 — The Hex Cheat Sheet

```
   Decimal  Hex  Binary        Decimal  Hex  Binary
   ───────  ───  ──────        ───────  ───  ──────
      0      0   0000              8     8   1000
      1      1   0001              9     9   1001
      2      2   0010             10     A   1010
      3      3   0011             11     B   1011
      4      4   0100             12     C   1100
      5      5   0101             13     D   1101
      6      6   0110             14     E   1110
      7      7   0111             15     F   1111

   ✨ The magic: ONE hex digit = exactly FOUR bits (a "nibble").
                 TWO hex digits = ONE byte.

   Binary  1100 1000      →   C   8    →   hex C8   = 200 decimal
   Binary  1111 1111      →   F   F    →   hex FF   = 255 decimal
```

You'll often see hex written with a `0x` in front (`0xFF`) so you know it isn't decimal.

### Where You'll See Hex in Security

| Where | Example | Chapter |
|---|---|---|
| **MAC addresses** | `3C:22:FB:9A:10:7E` | 4 |
| **IPv6 addresses** | `2001:0db8:85a3::8a2e:0370:7334` | 4 |
| **Hash values** | `5f4dcc3b5aa765d61d8327deb882cf99` | below |
| **Packet captures / memory dumps** | `48 65 6c 6c 6f` | 9 |
| **Colours on web pages** | `#FF0000` = red | — |

---

## 📖 Part 3 — Turning Text into Numbers (ASCII & Unicode)

Computers only store numbers, so every letter has an agreed number.

- **ASCII** is the original table. It uses 7 bits (128 characters) for English letters, digits and symbols.
- **Unicode (UTF-8)** extends this to every language and emoji (😀). It's what the modern web uses.

## 🖼️ Figure 3.3 — How "Hello" Is Stored

```
   Letter :     H         e         l         l         o
   Decimal:     72        101       108       108       111
   Hex    :     48        65        6C        6C        6F
   Binary : 01001000  01100101  01101100  01101100  01101111
```

> Fun fact: uppercase `A` is 65 (`0x41`) and lowercase `a` is 97 (`0x61`). To the computer they are completely different values. That's why passwords are **case-sensitive**.

---

## 📖 Part 4 — Encoding vs Encryption vs Hashing ⭐ (Very Important)

These three words sound similar, but they do very different jobs. Mixing them up is a classic beginner mistake, and a classic exam trap.

## 🖼️ Figure 3.4 — Three Ways to Transform a Message

```
                    ┌────────────────────────────────────────────────────┐
   "Hello"  ──────► │ ENCODING (Base64)                                  │ ──► "SGVsbG8="
                    │ Purpose: make data safe to TRANSPORT/STORE         │
                    │ Key?  NO     Reversible?  YES, by ANYONE           │
                    └────────────────────────────────────────────────────┘

                    ┌────────────────────────────────────────────────────┐
   "Hello"  ──🔑──► │ ENCRYPTION (e.g. AES)                              │ ──► "k8#Qz!..." (gibberish)
                    │ Purpose: keep data SECRET (confidentiality)        │
                    │ Key?  YES    Reversible?  YES, only WITH THE KEY   │
                    └────────────────────────────────────────────────────┘

                    ┌────────────────────────────────────────────────────┐
   "Hello"  ──────► │ HASHING (e.g. SHA-256)                             │ ──► "185f8db3..." (fixed length)
                    │ Purpose: prove data was NOT CHANGED (integrity)    │
                    │ Key?  NO     Reversible?  NO, ONE-WAY ONLY         │
                    └────────────────────────────────────────────────────┘
```

| | Encoding | Encryption | Hashing |
|---|---|---|---|
| **Goal** | Format/compatibility | **Confidentiality** (secrecy) | **Integrity** (no changes) |
| **Needs a key?** | No | **Yes** | No |
| **Can you get the original back?** | Yes, anyone can | Yes, with the key | **No (one-way)** |
| **Output length** | Grows with input | Grows with input | **Always the same length** |
| **Examples** | Base64, URL encoding, ASCII | AES, RSA | SHA-256, SHA-3, MD5 (old, broken) |
| **Real-life analogy** | Translating English into Morse code | Locking a letter in a safe | Taking a fingerprint |

> ⚠️ **Base64 is NOT encryption.** If you find a password stored as `cGFzc3dvcmQ=`, anyone can decode it back to `password` in one second. Security+ calls this kind of disguise **obfuscation**: it hides data but doesn't truly protect it.

### A Closer Look at Hashing: The Fingerprint 👆

A **hash function** takes any input (one word, or a whole movie) and produces a **fixed-length "fingerprint"** called a **hash** or **digest**.

## 🖼️ Figure 3.5 — Hashing in Action (real values)

```
  Input                    SHA-256 hash (always 64 hex characters = 256 bits)
  ──────────────────────   ────────────────────────────────────────────────────────────────
  password             →   5e884898da28047151d0e56f8dc6292773603d0d6aabbdd62a11ef721d1542d8
  Password             →   e7cf3ef4f17c3999a94f2c6f612e8a888e5b1026878e4e19398b23bd38ec221a
                            ▲
                            └── changing ONE letter changes the WHOLE hash ("avalanche effect")

  Input                    MD5 hash (always 32 hex characters = 128 bits)
  password             →   5f4dcc3b5aa765d61d8327deb882cf99
```

**Three magic properties of a good hash:**
1. **One-way:** you can't turn the hash back into the input. (You can't rebuild a person from a fingerprint.)
2. **Same input → same hash, every time.** This lets you check whether two things are identical.
3. **Tiny change → completely different hash.** Even one bit flipped is obvious.

**How hashing is used:**
- **Storing passwords:** websites should store the *hash* of your password, not the password itself. When you log in, they hash what you typed and compare the two hashes.
- **Checking downloads:** a website shows the SHA-256 of a file. You hash your downloaded copy. If the hashes match, the file wasn't tampered with.
- **Digital forensics:** investigators hash evidence to prove nobody changed it (Chapter 41).

> 🔐 **Why security cares:** If two *different* inputs ever produce the *same* hash, that's called a **collision**, and the hash function is considered broken. **MD5** and **SHA-1** have known collisions, so use **SHA-256** or better.

---

## 📖 Part 5 — Compression

**Compression** makes data smaller by removing repetition (e.g., `.zip` files). It's **not** a security feature. But:

- Attackers compress malware inside `.zip` files to sneak past email filters.
- Encrypted data looks random, so it **can't be compressed well**. Compress first, then encrypt.

---

## 🧠 Memory Tricks

- **Binary row:** "128, 64, 32, 16, 8, 4, 2, 1": just keep halving from 128.
- **1 hex digit = 4 bits; 2 hex digits = 1 byte.**
- **E-E-H:** **E**ncoding = **E**veryone can reverse · **E**ncryption = needs the **key** · **H**ashing = **H**alts, can't go back.
- **Hash = fingerprint, Encryption = safe, Encoding = Morse code.**

---

## ⚠️ Exam Tip

- *"Which technique ensures a file has not been altered?"* → **Hashing** (integrity).
- *"Which technique keeps data secret from unauthorized people?"* → **Encryption** (confidentiality).
- *"A developer stored passwords in Base64. What's wrong?"* → Base64 is **encoding, not encryption**. It's easily reversed. Passwords should be **hashed with a salt** (Chapter 28).
- *"Two different files produce the same hash. What attack is this?"* → A **collision** attack.

---

## 🧪 Try It (15 minutes)

**1. Practice binary.** Convert these to binary using the 128-64-32-16-8-4-2-1 row: `10`, `172`, `255`, `64`.

**2. Hash a file yourself:**

| OS | Command |
|---|---|
| Windows (PowerShell) | `Get-FileHash .\somefile.txt -Algorithm SHA256` |
| Windows (CMD) | `certutil -hashfile somefile.txt SHA256` |
| macOS | `shasum -a 256 somefile.txt` |
| Linux | `sha256sum somefile.txt` |

Now open the file, add one space, save it, and hash it again. The whole hash changes.

**3. Encode and decode Base64 (Linux/macOS terminal):**
```bash
echo -n "Hello" | base64          # → SGVsbG8=
echo "SGVsbG8=" | base64 --decode  # → Hello
```
Notice how there is no key and no secret. Anyone can reverse it.

---

## ✅ Checkpoint Questions

1. Convert binary `00001111` to decimal.
2. Convert decimal `172` to binary.
3. How many bits are in one hex digit?
4. What is hex `FF` in decimal?
5. Which one needs a key: encoding, encryption or hashing?
6. Which one can **never** be reversed to get the original input?
7. You download a program and its SHA-256 hash does **not** match the one on the official website. What should you conclude?
8. Why does adding just one bit to a key length make it twice as hard to brute-force?
9. A colleague says "our passwords are safe, they're stored in Base64." Are they right?
10. Why are passwords case-sensitive?

<details>
<summary><b>Show answers</b></summary>

1. 8 + 4 + 2 + 1 = **15**.
2. 128 + 32 + 8 + 4 = 172 → **10101100**.
3. **4 bits** (a nibble).
4. **255**.
5. **Encryption.**
6. **Hashing** (it is one-way).
7. The file was **changed**: corrupted, or tampered with (possibly malware). Don't run it.
8. Each extra bit **doubles** the number of possible keys the attacker must try.
9. **No.** Base64 is encoding, not encryption. Anyone can decode it instantly.
10. Uppercase and lowercase letters have **different numeric values** (e.g., `A` = 65, `a` = 97), so they produce different data and different hashes.

</details>

---

## 📌 Chapter Summary

| Concept | Key fact | Security link |
|---|---|---|
| Binary | Only 0 and 1. 8 bits = 1 byte = 0–255 | IP addresses, key lengths |
| Hexadecimal | 0–9, A–F. 1 hex digit = 4 bits | MAC/IPv6 addresses, hashes |
| ASCII/Unicode | Letters stored as numbers | Case-sensitive passwords |
| Encoding | Reversible by anyone, no key | Not security! (obfuscation only) |
| Encryption | Reversible only with a key | **Confidentiality** |
| Hashing | One-way, fixed-length fingerprint | **Integrity**, password storage |

**Next chapter →** *Chapter 4: Networking 101.* Now that you know how data looks, let's send it across the room and around the world.
