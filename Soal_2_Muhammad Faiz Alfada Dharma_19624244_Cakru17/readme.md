1. class Robot
class ini berfungsi untuk mendefinisikan robot, atributnya, dan metode menyerang dan bertahan.
- Atribut:
    id: untuk ID robot.
    name: Nama robot (str)
    health: HP robot (int)
    attack_type: Jenis attack yang digunakan robot (str).
    defense_type: Jenis defense yang akan digunakan robot (str).
    alive: untuk menunjukkan apakah robot masih hidup atau tidak (bool)
- Fungsi 
    a. attack(self, attack_type, target) = Robot attack robot yang lain (target) dengan beberapa jenis serangan dengan power yang beragam.  Jika health robot lain (target) setelah di attack di bawah nol, maka healthnya akan diatur ke nol.
    b. defense(self, defence_type) = Robot melakukan defense untuk menambah health (mengurangi damage dari serangan robot) sesuai dengan jenis defense yang dipilih.
    c. set_alive(self) = untuk memeriksa apakah robot masih hidup berdasarkan health nya 

2. class Battle
class ini berfungsi untuk mengatur pertarungan robot
- Atribut yang didefinisikan adalah robot_a dan robot_b, yaitu dua instance yang mewakili robot bertarung 
- Fungsi
    a. begin_battle(robot_a, robot_b) = digunakan untuk mengumumkan dimulainya pertarungan antar robot dan menampilkan nama robot yang bertarung.
    b. updateStatus(robot_a, robot_b, df) = Memperbarui DataFrame (df) untuk menampilkan health dan status robot (hidup atau mati).
    c. battle(robot_a, robot_b) = digunakan untuk melaksanakan pertarungan
        Setiap robot akan bergiliran untuk melakukan attack dan defense.
        Pertarungan akan terus berjalan sampai salah satu health robot mencapai 0 
        Setelah gerakan yang dilakukan robot (attack / defense), akan diperiksa apakah ada robot yang mati. Jika salah satu robot mati (health < 0) maka pertarungan berakhir 

3. class game
class ini berfungsi untuk mengatur alur pertarungan robot.
- Fungsi
    a. add_robot() = digunakan untuk meminta input (yes/no) untuk memulai pertarungan. Jika input adalah "yes" maka pertarungan dimulai. Jika "no" maka program akan keluar.
    b. robot_selected(robot_a, robot_b) = digunakan untuk menampilkan robot yang dipilih untuk bertarung.
    c. robot_available(robot_a, robot_b) = digunakan untuk menampilkan daftar robot yang available untuk bertarung
    d. start_game() = terdapat beberapa proses pada def start_game
        akan memfilter data frame (df) untuk memilih robot yang masih hidup.
        akan dipilih dua robot secara acak untuk bertarung.
        instance robot (robot_a dan robot_b) akan dibuat pada tahap ini berdasarkan data yang dipilih.
        #Begin battle, digunakan untuk memanggil fungsi untuk mulai pertarungan dan memperbaharui data frame dengan hasilnya.

4. global variable dan data frame
    a. attack_type dan defence_type:
    b. initial_health:
        health robot sebelum bertarung diatur menjadi 100 untuk setiap robot
    c. df:
        data frame yang berisi data-data robot yaitu:
            Kolom: id, nama (nama), health, dan alive.
            Baris: tiga robot dengan id 1, 2, dan 3, initial health adalah 100 dan semuanya masih berstatus hidup / alive.

5. Running program
    Program dimulai dengan memanggil Game.add_robot() yang akan meminta untuk memulai pertarungan.
    Jika memasukkan input "yes" maka dilanjutkan pertarungan
        Game.start_game() dipanggil akan memilih dua robot secara random dari data frame dan memulai pertarungan
        Setelah battle selesai hasilnya diperbarui di data frame (df), dan hasil pertarungan ditampilkan di output, yang berisi robot mana saja yang masih hidup beserta sisa health nya. 