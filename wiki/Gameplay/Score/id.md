# Skor

::: alert-note
**Catatan:** [Skor (disambiguasi)](/wiki/Disambiguation/Score).
:::

Skor akan diberikan kepada pemain setelah menyelesaikan suatu [beatmap](/wiki/Beatmap) yang dihitung berdasarkan [judgments](/wiki/Gameplay/Judgement) yang didapatkan pemain untuk setiap [objek ketukan](/wiki/Gameplay/Hit_object). Sistem skoring yang digunakan di bagi menjadi dua versi besar.

## ScoreV1

ScoreV1 adalah sebutan umum untuk sistem skoring bawaan di osu!. Meskipun biasanya disebut dengan satu nama, algoritma hitungannya berbeda berdasarkan [mode permainan](/wiki/Game_mode) yang dipilih:

- osu! dan osu!catch menggunakan pengali skor berbasis kombo yang diterapkan secara ketat pada setiap objek ketukan.
- osu!taiko roughly follows the *Taiko no Tatsujin* scoring system with a small constant score affected with combo bonus -- osu!taiko secara garis besar mengikuti sistem skoring *Taiko no Tatsujin* dengan skor dasar yang kecil tetap dan dipengaruhi oleh bonus kombo. 
- osu!mania adalah satu-satunya mode permainan yang memiliki batas skor (di ScoreV1), yang mana ditetapkan pada nilai 1,000,000 dengan [pengali skor](/wiki/Gameplay/Game_modifier/Mod_multiplier) 1,00x.

Untuk penjelasan lebih rinci tentang cara ScoreV1 bekerja di setiap mode permainan, lihat:

- [osu!](ScoreV1/osu!)
- [osu!taiko](ScoreV1/osu!taiko)
- [osu!catch](ScoreV1/osu!catch)
- [osu!mania](ScoreV1/osu!mania)

## ScoreV2

ScoreV2 is a new iteration of the scoring system. The main idea behind it is standardisation of all the game modes' scoring systems, such that a perfect score is awarded 1,000,000 points at 1.00x score modifier, with additional score gains on top of that from spinner bonuses for osu!, drumrolls for osu!taiko, and bananas for osu!catch. This implies a departure from the original scoring values of each hit object, and a change to a system that is more centred around proportions and scaling to the 1 million cap.

Aside from improved standardisation, ScoreV2 is also a workaround for an [integer overflow](https://en.wikipedia.org/wiki/Integer_overflow) issue that can arise on long and combo-intensive maps. Because the total score is stored as a 32-bit integer and ScoreV1 can theoretically give an unlimited amount of score, exceeding the maximum representable 32-bit integer score value of 2,147,483,647 points would cause the score counter to wrap around to negative values (which is visually seen as the score proceeding to count backwards). In practice, ScoreV2 is automatically enabled for scores set on long beatmaps that would otherwise have a maximum score above the 32-bit integer limit.

ScoreV2 is not enabled by default in gameplay; in solo play, it can be enabled through the unranked [ScoreV2](/wiki/Gameplay/Game_modifier/ScoreV2) game modifier, and in [multiplayer](/wiki/Client/Interface/Multiplayer), ScoreV2 can be set as a win condition during match setup.
