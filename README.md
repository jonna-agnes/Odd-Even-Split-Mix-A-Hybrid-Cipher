# Odd-Even-Split-Mix-A-Hybrid-Cipher
This hybrid cipher encrypts messages in two stages: it splits the plaintext into odd and even-positioned letters. Odd letters are encrypted using the Playfair cipher, while even letters are reversed and encrypted using Caesar substitution. The final ciphertext combines both encrypted parts.

# Rules
 1. Number letters left→right starting at 1.
 2. Odd letters = positions 1,3,5,... — we keep their left→right order. Encrypt these with Playfair.
 3. Even letters = positions 2,4,6,... — take them but reverse their order (take from the back). 
Encrypt those with ceaser substitution.
 4. Final ciphertext = Playfair-output (odds) + ceaser-output (evens).
 5. To decrypt: split back using counts, decrypt each part, reverse the even sequence back, then re
insert odds and evens into original positions.

⚡ Encryption Process

Odd–Even Split

Split each word into odd-positioned and even-positioned letters.

Example: "BIRIYANI" → Odd = BRYN, Even = IIAI.

Odd Letters → Playfair Cipher

Odd letters are encrypted using Playfair (5×5 key matrix).

Pairs are formed and processed with Playfair rules (same row, same column, rectangle).

Example: BRYN → DAGY.

Even Letters → Caesar Shift

Even letters are reversed, then shifted by +2 (monoalphabetic substitution).

Example: IIAI → IAII → KCKK.

Mix

Final ciphertext = Playfair(odd) + Caesar(even).

Example: "BIRIYANI" → DAGYKCKK.

🔄 Decryption Process

Split Ciphertext into Playfair part (odd letters) and Caesar part (even letters).

Decrypt Caesar by reversing the +2 shift (i.e., −2), then reverse string back.

Decrypt Playfair pairs using inverse rules (left/up/rectangle swap).

Recombine Odd + Even to restore the original plaintext.

✅ Example

Plaintext:

BIRIYANI IS THE BEST


Ciphertext:

DAGYKCKK SAU LKZJ IXVG


Decryption:

BIRIYANI IS THE BEST
