label start:

```
scene forest_night with fade
play music "mystic_forest.ogg" fadein 1.0

narrator "Malam itu, di tengah hutan yang dingin dan sunyi, seorang anak dibuang. Dunia menolaknya tanpa belas kasihan."

show raviel_child scared at center
show shadowy_figure at right

shadowy_figure "Jangan takut, anak buangan. Aku yang akan membesarkanmu. Dunia ini penuh kebencian, dan kau akan menjadi senjataku."

scene ruins_day with fade
stop music fadeout 1.0
play music "dramatic_theme.ogg" fadein 1.0

narrator "Sepuluh tahun kemudian, Raviel berdiri di atas runtuhan kota yang sunyi."

show raviel_adult determined at center

raviel "Dunia ini yang mencipta aku. Dan aku akan membalasnya dengan kekuatan yang mereka tak pernah fahami."

show ren_shining at left with dissolve

ren "Raviel, hati yang terluka bukan jalan menuju kehancuran. Masih ada ruang untuk berubah."

menu:
    "Aku tak perlukan belas kasihan.":
        jump raviel_reject
    "Kenapa kau peduli padaku?":
        jump ren_explain
    "Serang Ren dengan kuasa gelap!":
        jump attack_ren
```

label raviel\_reject:

```
raviel "Belas kasihan itu kelemahan. Aku hanya tahu balas dendam."

ren "Dendam itu beban berat yang hanya akan menghancurkanmu."

jump battle_start
```

label ren\_explain:

```
ren "Aku tahu bagaimana rasanya disakiti. Tapi aku memilih untuk tidak membiarkan luka itu menguasai hidupku."

raviel "Kau mungkin berbeza, tapi aku tidak sehebat itu."

jump battle_start
```

label attack\_ren:

```
raviel "Kalau begitu, aku takkan tahan lagi!"

# Tambah animasi serangan sihir gelap

jump battle_start
```

label battle\_start:

```
narrator "Pertarungan antara dua kuasa bermula, cahaya melawan kegelapan."

# Animasi pertarungan dan suara sihir

ren "Ini belum selesai, Raviel... sesuatu yang lebih gelap sedang mendekat."

raviel "Apa lagi yang kau sembunyikan, dunia ini?"

scene black with fade
stop music fadeout 1.0

narrator "Pertarungan mereka terganggu oleh kehadiran sesuatu yang misteri..."

jump chapter_two
```

label chapter\_two:

```
scene temple_interior with fade
play music "memory_theme.ogg" fadein 1.0

narrator "Ren membawa Raviel ke sebuah kuil tersembunyi di tengah hutan, tempat yang menyimpan sejarah luka dan harapan."

show ren_shining at center

ren "Di sini aku belajar untuk melepaskan kebencian. Mungkin kau juga boleh menemui jawapan."

show raviel_adult tired at right

raviel "Kenapa kau masih mahu tolong aku? Aku boleh membunuhmu bila-bila masa."

ren "Kerana aku nampak diriku dalam dirimu. Tapi aku buat pilihan untuk berubah."

narrator "Raviel terduduk, fikirannya keliru. Pemain diberi peluang untuk memilih jalan seterusnya."

menu:
    "Tanya tentang kisah silam Ren.":
        jump ask_past
    "Diam dan renung masa lalu sendiri.":
        jump reflect_self
    "Tinggalkan kuil tanpa kata.":
        jump leave_temple
```

label ask\_past:

```
raviel "Ceritakan padaku... apa yang berlaku padamu sebenarnya?"

ren "Aku pernah kehilangan keluargaku... dibakar hidup-hidup oleh mereka yang takut kepada kuasa cahaya. Aku hampir jadi seperti kau. Tapi seseorang menyelamatkanku, sama seperti aku cuba selamatkan kau sekarang."

raviel "...Aku tak sangka."

jump inner_conflict
```

label reflect\_self:

```
narrator "Raviel merenung tangannya. Ingatan masa kecilnya datang kembali – malam dia ditinggalkan, malam dia dipeluk oleh kegelapan."

raviel "Adakah... aku benar-benar telah hilang arah?"

jump inner_conflict
```

label leave\_temple:

```
narrator "Tanpa berkata apa-apa, Raviel bangkit dan melangkah keluar dari kuil. Ren hanya melihat dengan mata sayu."

ren "Kadang-kadang... perubahan hanya datang apabila kita berjalan sendiri."

jump inner_conflict
```

label inner\_conflict:

```
narrator "Dalam tidur malam itu, Raviel bermimpi. Dia melihat bayangan dirinya diselubungi cahaya dan kegelapan – dua takdir yang saling bertembung."

show dream_raviel_dark at left
show dream_raviel_light at right

narrator "Pemain melihat bar moral Raviel berubah sedikit, berdasarkan pilihan yang telah dibuat."

stop music fadeout 1.0
scene black with fade
narrator "Keesokan paginya, takdir Raviel mulai terbentuk..."

jump chapter_three
```

label chapter\_three:

```
scene city_ruins_day with fade
play music "tension_theme.ogg" fadein 1.0

narrator "Dunia luar kini menyedari kewujudan Raviel. Kerajaan mengeluarkan perintah tangkap terhadapnya, menganggapnya sebagai ancaman."

show soldier at left
show messenger at right

messenger "Tuanku, Raviel telah dilihat berhampiran kuil purba."
soldier "Kumpulkan pasukan. Kita tamatkan ancaman ini."

scene mountain_pass with fade
show raviel_adult thinking at center

narrator "Raviel berdiri di laluan gunung, memerhati dari jauh. Fikirannya berperang antara dendam dan peluang untuk berubah."

menu:
    "Aku akan hancurkan mereka semua.":
        jump path_dark
    "Aku hanya ingin mereka faham aku.":
        jump path_neutral
    "Aku tak mahu lagi menyakiti sesiapa.":
        jump path_light
```

label path\_dark:

```
$ raviel_morality = "dark"
narrator "Raviel memilih kegelapan. Dia menyalurkan kuasa gelapnya dan menyerang kampung terdekat."
show fire_effect
play sound "dark_blast.ogg"

narrator "Tiada belas kasihan. Tiada undur. Dunia akan rasa derita seperti yang dia alami."
jump chapter_four
```

label path\_neutral:

```
$ raviel_morality = "neutral"
narrator "Raviel tidak bertindak melulu. Dia mula mencari mereka yang faham penderitaannya, dan cuba berdamai dengan sesetengah pihak."

show npc_ally at left
npc_ally "Aku tahu kau bukan sekejam yang mereka kata. Aku akan bantu kau."

jump chapter_four
```

label path\_light:

```
$ raviel_morality = "light"
narrator "Raviel memilih untuk tidak lagi menjadi alat kebencian. Dia menyelamatkan sebuah perkampungan daripada serangan, meskipun mereka takut padanya."

show villagers_scared
play music "hope_theme.ogg"

narrator "Perlahan-lahan, harapan mula tumbuh. Tapi jalan menuju penebusan masih panjang."
jump chapter_four
```

label chapter\_four:

```
scene final_battlefield with fade
play music "epic_final.ogg" fadein 1.0

narrator "Pertarungan terakhir bermula. Entiti Gelap, penjaga Raviel, muncul dalam bentuk sebenar – raksasa bayangan yang mahu menghancurkan dunia."

show dark_entity at center
show raviel_adult at left
show ren_shining at right

if raviel_morality == "dark":
    raviel "Akhirnya aku kembali padamu... Guru. Dunia ini akan terbakar bersama kita."
    dark_entity "Anakku... mari kita tamatkan segalanya."
    narrator "Ren cuba menghalang, tetapi kuasa gabungan Raviel dan Entiti Gelap terlalu kuat. Dunia hancur. Tamat buruk."
    return

elif raviel_morality == "neutral":
    raviel "Aku tak tahu siapa aku lagi. Tapi aku tak mahu dunia ini musnah."
    ren "Kalau begitu, lawanlah dia bersamaku!"
    narrator "Raviel dan Ren menentang Entiti Gelap. Pertarungan sengit berlangsung. Dunia diselamatkan, tapi Raviel cedera parah dan hilang. Tamat neutral."
    return

elif raviel_morality == "light":
    raviel "Aku bukan lagi anak kegelapan! Aku adalah Raviel – penjaga harapan."
    ren "Bersamalah kita bawa cahaya ke dunia ini!"
    narrator "Raviel dan Ren menyatukan kuasa, menghapuskan Entiti Gelap dan memulihkan dunia. Raviel menjadi simbol penebusan. Tamat baik."
    return

else:
    narrator "Takdir Raviel masih kabur. Tetapi satu perkara pasti – dunia akan ingat namanya."
    return
```
![file_0000000081d061f596913e37ec179c7c](https://github.com/user-attachments/assets/f522e88b-2c4a-4b08-a8e8-6fe1aea1b42b)
