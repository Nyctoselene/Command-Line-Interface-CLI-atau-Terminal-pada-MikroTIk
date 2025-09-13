# Command-Line-Interface-(CLI)-atau-Terminal-pada-MikroTIk

LAB 4
Command Line Interface [CLI/Terminal] pada MikroTik

![Topo](Topo.png) 

Selain menggunakan winbox yang sangat user friendly dengan mode GUI nya, MikroTik juga dapat dikonfigurasi menggunakan mode CLI (berbasis teks/text mode).\
Pada Repo sebelumnya, Mikrotik router OS dapat dikonfig melalui CLI / terminal menggunakan akses/remote via: Winbox (terminal), PuTTY(ssh dan telnet), cmd(telnet), console dan Aplikasi Mikrotik Pro.  

Mode CLI biasanya digunakan untuk user tingkat lanjut atau expert, terutama yang belajar menggunakan aplikasi GNS3 dan EVE-NG, karena lebih simple untuk langsung konfigurasi mikrotik tanpa harus menggunakan Winbox.

Berikut ini perintah-perintah dasar pada mikrotik melalui terminal:

Mengganti identitas mikrotik

    [admin@MikroTik] > system identity set name=RB-Belajar
    [admin@RB-Belajar] > 
    
     #(masukkan nama identity baru pada bagian name= )
Memberikan password admin

    [admin@RB-Belajar] > password
Setelah itu akan muncul tampilan untuk memasukkan password baru

    old-password:
    new-password:********
    confirm-new-password:********
    
     #(karena old password nya adalah password bawaan dari MikroTik (yaitu blank) maka bagian old password tidak perlu diisi) 
Membuat user baru dan password dengan hak akses full

    [admin@RB-Belajar] > user add name=Salman group=full password=admin123
    
     #(ada tiga jenis group:
     read = hanya bisa membaca tidak bisa mengonfigurasi
     write = dapat mengonfigurasi namun tidak dapat menambahkan user login baru dan melakukan reset configuration pada router
     full = mempunyai akses full dalam mengonfigurasi) 
Melihat user

    [admin@RB-Belajar] > user print
    Flags: E - expired, X - disabled
    #     NAME        GROUP        ADDRESS                       LAST-LOGGED-IN
    0     ;;; system default user
          admin       full                                       sep/12/2024 00:03:36
    1     Salman      full
    [admin@RB-Belajar] > 
Melihat Lisensi

    [admin@RB-Belajar] > system license print
      software-id: W716-FUJ3
           nlevel: 4
         features:
    [admin@RB-Belajar] > 
Mengganti nama interface dan Melihat interface

    [admin@RB-Belajar] > interface set name=Ether1-WAN ether1
    [admin@RB-Belajar] > interface set name=Ether2-LAN ether2
    [admin@RB-Belajar] > interface print
    Flags: D - dynamic, X - disabled R - running, S - slave
     #     NAME                               TYPE       ACTUAL-MTU L2MTU
     0  R  Ether1-WAN                         ether            1500  1598
     1  R  Ether2-LAN                         ether            1500  1598
     2     Ether3                             ether            1500  1598
     3     Ether4                             ether            1500  1598
     4     Ether5                             ether            1500  1598

     [admin@RB-Belajar] > 
Memberikan IP Address 192.168.10.1/24 dan Melihat IP Address

     [admin@RB-Belajar] > ip address add address=192.168.10.1/24 interface=Ether1-WAN
     [admin@RB-Belajar] > ip address print
     flags: X - disabled, i - invalid, D - dynamic
      #   ADDRESS            NETWORK         INTERFACE
      0   192.168.10.1/24    192.168.10.1    Ether2-LAN
     [admin@RB-Belajar] > 
Mengedit IP Address 192.166.10.1/24 menjadi 192.168.20.1/24 dan Melihat IP Address

![Edit IP](Edit%20IP.png)

Menambahkan perintah NAT dan Melihat konfigurasi NAT

![NAT](NAT.png)

Menambahkan gateway dan Melihat gateway

![Gateway](Gateway.png)

Menambahkan DNS dan Melihat DNS 

![DNS](DNS.png)

Melakukan ping

![Ping](Ping.png)

Klik Tab pada Keyboard dua kali untuk melihat perintah apa saja yang dapat digunakan

![Available Comms](Available%20Comms.png)

Klik ? pada Keyboard untuk melihat semua perintah dan pengertiannya

![List of Comms](List%20of%20Comms.png)

Menyingkat perintah

![Singkat](Singkat.png)

Ketik “..” untuk kembali ke direktori sebelumnya

![Prevdir](Prevdir.png)


Kesimpulan : 
Mode CLI biasanya digunakan untuk user tingkat lanjut atau expert, terutama yang belajar menggunakan aplikasi GNS3 dan EVE-NG, karena lebih simple untuk langsung konfigurasi mikrotik, tanpa harus menggunakan winbox.
Pada mode CLI terdapat menu bantuan menggunakan tab dan tanda tanya(?) yang memudahkan user dalam menggunakan mode CLI.

Sekian yang dapat saya sampaikan, mohon maaf apabila ada salah kata atau kekurangan dalam penyampaian. Akhir kata, Wassalam
