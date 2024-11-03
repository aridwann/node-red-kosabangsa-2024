## Cara setup web monitoring kosabangsa 2024

### Mosquitto
1. Install mosquitto
2. run `mosquitto` di cmd
3. run `mosquitto_passwd -c C:\[path]\mosquitto\passwd user1` di cmd dan masukkan password *path disesuaikan
4. buka `mosquitto\mosquitto.conf`, lalu tambahkan  
   `password_file /path/mosquitto/passwd` *sesuaikan path
   `allow_anonymous false`
5. Testing:  
   cmd subscriber : `mosquitto_sub -h localhost -t test/topic`  
   cmd publiser : `mosquitto_pub -h localhost -t test/topic -m "Hello, Mosquitto!"`

### Python
1. Install python
2. Install opencv-python dan flask dengan `pip install opencv-python flask`
3. Unduh file `server.py`
4. Sesuaikan index dengan urutan kamera
5. Untuk menjalankan bisa dengan `python server.py`
6. Camera bisa diakses pada `http://localhost:5000/video_feed`

### Node-red
1. Install node.js
2. Install node-red
3. Run `node-red`
4. Import file `node-red-flow.json`
5. Ganti nilai `src` pada nodes `camera` dengan `http://localhost:5000/video_feed`, sesuaikan `localhost`
6. Matikan terlebih dahulu `firewall` saat mengakses `http://localhost:1883/dashboard`, agar video pada `camera` bekerja pada device lain (handphone)  

### Run After Startup
1. Tekan `Win + R`, ketik `shell:startup`, dan tekan Enter.
2. Klik kanan di dalam folder Startup dan pilih New > Shortcut.  
   a. Untuk node-red masukkan : `"C:\Users\<NamaPengguna>\AppData\Roaming\npm\node-red.cmd"`  
   b. Untuk eksekusi python masukkan : `"C:\path\to\python.exe" "C:\path\to\namafile.py"`  
   c. Untuk mosquitto : `"C:\path\to\mosquitto.exe"`
   * Sesuaikan path
4. Simpan Shortcut dan tutup folder. Saat komputer di-restart, perintah di dalam folder Startup akan dijalankan secara otomatis.
   
Berikut nodes nya:  
![image](https://github.com/user-attachments/assets/a7fa864f-1bad-4e98-bc6b-5bd9128d10b6)


