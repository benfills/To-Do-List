# To-Do App (MVP)

Proyek to-do list sederhana buat belajar FullStack. 


# Tech
- HTML/CSS/JS
- Backend: (Belum Ditentuin)
- Database: PostgreSQL



# Tim
- Zllal = Desain UI  
- Ri = Layout (HTML/CSS)  
- Refa = Auth 
- Vadlan = Tasks Backend / DB  


# Roadmap

## **FASE 0 — PLANNING (SEMUA ORANG)**

🟢**Fitur:**

* Login / Register
* Tambah Task
* Lihat Task List
* Beralih Done (toggle)
* Hapus Task
* Deadline Hapus Permanent (30 Hari)
* Hapus Permanen
* Notifikasi
* (Klo mau nambah boleh)

🔵**UserFlow:** *(otw)*

⚪**Style Guide:**

---

## **FASE 1 UI DESAIN (AZLAL)**

⚪ Buat mockup GUI utama (Task List)

⚪ Buat mockup Login & Register

⚪ Fix warna, font, spacing

---

## **FASE 2 LAYOUT UI (RIZKI)**

⚪ Coding tampilan Login / Register

⚪ Coding tampilan Task List

⚪ Buat komponen (Add, List, Toggle)

---

## **FASE 3A AUTH LOGIN/REGISTER (REVA)**

⚪ POST `/auth/register`

⚪ POST `/auth/login`

⚪ Hash password

⚪ JWT + Middleware

⚪ Return `user_id` dalam `req` untuk backend tasks

---

## **FASE 3B DB + QUERY + CRUD (VADLAN)**

⚪ Buat tabel `tasks`

⚪ POST `/tasks`

⚪ GET `/tasks`

⚪ PATCH `/tasks/:id` (toggle)

⚪ DELETE `/tasks/:id`

⚪ Query harus hanya menampilkan task milik `user_id` terkait

---

## **FASE 4 INTEGRASI (SEMUA)**

⚪ Rizki sambungkan UI ke Auth

⚪ Rizki sambungkan UI ke CRUD Tasks

⚪ Test alur lengkap:

  * Login → Masuk → Tambah Task
  * Toggle → Delete

---

## **FASE 5 MVP DONE (APP JALAN)**

⚪ GUI → Auth → Task CRUD bekerja smooth
