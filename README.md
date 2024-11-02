## Cara pemakaian singkat
1. Install opencv-python dan flask dengan `pip install opencv-python flask`  
2. Jalankan file `server.py` dengan `python server.py`  
3. Import file `node-red-flow.json`  
5. Ganti nilai `src` pada nodes `cam1` dan `cam2` dengan `http://localhost:5000/video_feed`, sesuaikan `localhost`  
6. Matikan terlebih dahulu `firewall` saat mengakses node red dashboard, agar video pada `cam1` dan `cam2` bekerja pada device lain (handphone)
