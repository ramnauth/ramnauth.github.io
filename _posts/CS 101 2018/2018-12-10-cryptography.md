---
# Posts need to have the `post` layout
layout: post

# The title of your post
title: Cryptography
# (Optional) Write a short (~150 characters) description of each blog post.
# This description is used to preview the page on search engines, social media, etc.
description: >
   

# (Optional) Link to an image that represents your blog post.
# The aspect ratio should be ~16:9.
image: /assets/img/default.jpg

# You can hide the description and/or image from the output
# (only visible to search engines) by setting:
# hide_description: true
# hide_image: true

# (Optional) Each post can have zero or more categories, and zero or more tags.
# The difference is that categories will be part of the URL, while tags will not.
# E.g. the URL of this post is <site.baseurl>/hydejack/2017/11/23/example-content/
categories: [CS 101]
tags: []
# If you want a category or tag to have its own page,
# check out `_featured_categories` and `_featured_tags` respectively.
---

The word 'cryptography' comes from **crypto** meaning "secret" and **graphy** meaning "writing". So, the idea of cryptography is that we want to send
messages that can be understood only by its **intended recipient**. 

Like castles, there are several layers of **encryption** or protection that can be used. For example, to get past its security (**decrypt**), you may have to
successfully escape the archers, get past the moat, and figure your way through the maze of rooms and guards to get to the throne room (in this analogy, the king is the **plaintext** message -- aka the secret you're trying to find out). 

When so many layers of protection are involved, we call this **defense in depth**. Many cryptographic algorithms (aka **ciphers**) use defense in depth to make it more difficult to "crack the code".

## Caesar Cipher
The Caesar cipher is perhaps the earliest known cipher. It a type of **substitution cipher** where each letter in the plaintext maps directly to another letter. How? A Caesar cipher, particularly, 'shifts' the entire alphabet a certain **key**. In the case of the Caesar cipher, this key is a whole number.

For example, with a key of 1, `A` would be replaced by `B`, `B` becomes `C`, `C` becomes `D`, and so on. As you may have guessed, this method is named after Julius Caesar, an emperor of Ancient Rome, who used this cipher to communicate military commands with his generals. 

```
Actual Alphabet:  A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
Shifted Alphabet: Z A B C D E F G H I J K L M N O P Q R S T U V W X Y

Message:        ATTACKATDAWN
Encrypted:      ZSSZBJZSCZVM
```

To pass an encrypted message from one person to another, it is necessary that both people/parties have the key for the cipher, so the sender may *encrypt* it and the receiver may *decrypt* it. 

However, the Caesar cipher isn't too hard to crack. Try to determine the key and decrypt the following encrypted message:
```
efgfoe uif fbtu xbmm pg uif dbtumf
```

Using a **brute-force** decryption method, you may try all possible keys for the Caesar cipher. There are only 26 keys (actually 25, because a key of `0` doesn't really encrypt the message). Guaranteeing a successfully decryption after trying only 25 possibilities demonstrates that the Caesar cipher isn't very secure.

Instead of a brute-force attack, you can quicken the decryption process by considering **frequency analysis**. We know that some letters appear more frequent than other letters in English text (see the [Oxford Math Center](http://www.oxfordmathcenter.com/drupal7/node/353) for a ranking of letters by frequency in the Oxford English Corpus). 
To decrypt the message above, we can rank the letters by its frequency and from there determine which letter it truly is. For example, in `efgfoe uif fbtu xbmm pg uif dbtumf`, the letter `F` appears 6 times and is most frequent, so we can conclude that `F` may map to `E` (the most frequent letter in the English language). Determining the frequencies of the remaining letters can you **decipher** the message?

Ultimately, the Caesar cipher is a part of a larger group of ciphers called **single substitution ciphers** aka **monoalphabetic ciphers**. Single substitution ciphers can easily be cracked using frequency analysis because each letter is singly mapped to another letter to both encrypt and decrypt.

## Vigenère Cipher

The Vigenère cipher is a **polyalphabetic substitution cipher** because it uses multiple substitution alphabet. Unlike the Caesar cipher which uses one **rotated** alphabet, the Vigenère cipher uses all 26 **permutations** of the English alphabet. 

The Vigenère cipher was considered "le chiffre ind hiffrable" (French for "the unbreakable cipher") for 300 years. Gilbert Vernam worked on the Vigenère cipher in the early 1900s and his work eventually led to the one-time pad encryption method, which is a provably unbreakable cipher.

The 'key' for a Vigenère cipher is a key *word*, e.g., `FORTIFICATION`. Using the following substitution table (which lists all *permutations* of the English alphabet), we can encipher and decipher a message. 
```
    A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
    ---------------------------------------------------
A   A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
B   B C D E F G H I J K L M N O P Q R S T U V W X Y Z A
C   C D E F G H I J K L M N O P Q R S T U V W X Y Z A B
D   D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
E   E F G H I J K L M N O P Q R S T U V W X Y Z A B C D
F   F G H I J K L M N O P Q R S T U V W X Y Z A B C D E
G   G H I J K L M N O P Q R S T U V W X Y Z A B C D E F
H   H I J K L M N O P Q R S T U V W X Y Z A B C D E F G
I   I J K L M N O P Q R S T U V W X Y Z A B C D E F G H
J   J K L M N O P Q R S T U V W X Y Z A B C D E F G H I
K   K L M N O P Q R S T U V W X Y Z A B C D E F G H I J
L   L M N O P Q R S T U V W X Y Z A B C D E F G H I J K
M   M N O P Q R S T U V W X Y Z A B C D E F G H I J K L
N   N O P Q R S T U V W X Y Z A B C D E F G H I J K L M
O   O P Q R S T U V W X Y Z A B C D E F G H I J K L M N
P   P Q R S T U V W X Y Z A B C D E F G H I J K L M N O
Q   Q R S T U V W X Y Z A B C D E F G H I J K L M N O P
R   R S T U V W X Y Z A B C D E F G H I J K L M N O P Q
S   S T U V W X Y Z A B C D E F G H I J K L M N O P Q R
T   T U V W X Y Z A B C D E F G H I J K L M N O P Q R S
U   U V W X Y Z A B C D E F G H I J K L M N O P Q R S T
V   V W X Y Z A B C D E F G H I J K L M N O P Q R S T U
W   W X Y Z A B C D E F G H I J K L M N O P Q R S T U V
X   X Y Z A B C D E F G H I J K L M N O P Q R S T U V W
Y   Y Z A B C D E F G H I J K L M N O P Q R S T U V W X
Z   Z A B C D E F G H I J K L M N O P Q R S T U V W X Y
```

To encrypt a message, repeat the keyword above the plaintext:
```
Key:     FORTIFICATIONFORTIFICATIONFO
Message: DEFENDTHEEASTWALLOFTHECASTLE
```

Now we take the letter we're encoding, `D`, and its corresponding letter in the key, `F`, and we find the intersection of column `D`, row `F`. We find that the encrypted character is `I`.

So the **ciphertext** for the above plaintext is:
```
Key:       FORTIFICATIONFORTIFICATIONFO
Message:   DEFENDTHEEASTWALLOFTHECASTLE
Encrypted: ISWXVIBJEXIGGBOCEWKBJEVIGGQS
```

To go backwards or to decrypt a message, we would have to know the key. Continuing with the previous example:
```
Key:       FORTIFICATIONFORTIFICATIONFO
Encrypted: ISWXVIBJEXIGGBOCEWKBJEVIGGQS
```

We want to decrypt the message and we know the key. We can work backwards by, for example, going to 
row `F` (the letter from the key) and following along until we find an `I` (the letter in the encrypted message) in the same row. Then, we travel up, to see that it falls under column `D`. We'd repeat this process until we have decoded all the letters in the encrypted message.

## One-Time Pads

A one-time pad is an encryption technique that cannot be cracked. That's because:
1. the pads (aka keys) are truly and completely random, and
2. They are never reused.

We could easily break a single-substitution cipher using frequency analysis. We can't so much in the Vigenère cipher (but it's still possible). 
But we definitely can't with one-time pads. Because the pads are randomly determined, the frequencies are almost uniform. There's no correlation between frequent letters in the encrypted message and frequent letters in the decrypted message.

Here's an example of a one-time pad:
```
KGMKJ KGBST NWGNR BBFGA FJUPK DRUIF ZMOPU PMCAS HHWCS LCKMA ZWLVZ FVPFH
YUGKX VJPXF HFEZQ GCMIT CZYGO UYESJ VUVJA UALLK YHEVT GPJZG SHMZI TQTDW
```

Suppose we want to encrypt the message `ATTACK AT DAWN` using this pad:
```
Message:   ATTAC KATDA WN
Encrypted: KGMKJ KGBST NW
```

Then, you just map the letters to the numbers using modular arithmetic. So `K + A` = `10 + 0` = `K`. Then `G + T` = `6 + 19` = `25` = `Z`. Next, `M + T` is `12 + 19` = `31 % 26` = `5` = `F`. And so on. The fully encoded message is:
```
KZFKLUGUVTJJ
```

## Public Key Systems
A serious drawback of all the above cryptography techniques is that the sender and receiver must establish a **shared secret**. The process in which they do that can be insecure. That is, if an **eavesdropper** is listening in which the parties are communicating their alphabet permutation or password, then their 'secret' message isn't very secret.

The invention of public-key cryptography removes this disadvantage by splitting the key into two parts: one that is *fully public* and one that is *fully private*.

## Resources
- [Caesar Cipher & Frequency Analysis](https://www.youtube.com/watch?v=sMOZf4GN3oc)(2:36)
- [Polyalphabetic Cipher](https://www.youtube.com/watch?v=BgFJD7oCmDE)(2:26)
- [One-Time Pads](https://www.youtube.com/watch?v=FlIG3TvQCBQ)(2:55)
- [Public-Key - Diffie-Hellman](https://www.youtube.com/watch?v=3QnD2c4Xovk)(5:23)
- [Public-Key - RSA](https://www.youtube.com/watch?v=wXB-V_Keiu8)(16:30)
- [General Overview of Cryptographic Techniques](https://www.youtube.com/watch?v=jhXCTbFnK8o)