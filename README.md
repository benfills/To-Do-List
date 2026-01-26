# ✪ To-Do App (MVP)

Proyek to-do list sederhana buat belajar FullStack. 


# ✪ Tech
- HTML/CSS/JS
- Backend: Node.js(Fastify)
- Database: PostgreSQL



# ✪ Tim
- Azlal = Desain UI  
- Rizki = Layout (HTML/CSS)  
- Refa = Auth 
- Vadlan = Tasks Backend / DB  


# ✪ Roadmap

## **FASE 0 PLANNING (SEMUA ORANG)**

🟢**Fitur:**

* Login / Register
* Tambah Task
* Lihat Task List
* Beralih Done (toggle)
* Hapus Task
* Deadline Hapus Permanent (30 Hari)
* Hapus Permanen
* Notifikasi per task
* (Klo mau nambah boleh)

🔵**UserFlow:**

TO-DO APP
│
├─ ENTRY APLIKASI
│   │
│   ├─ Buka URL
│   │   │
│   │   ├─ JWT valid?
│   │   │   ├─ YA  → Task List
│   │   │   └─ TIDAK → Login Page
│   │   │
│   │   └─ (401) → Clear Token → Login
│
├─ AUTH
│   │
│   ├─ Register
│   │   │
│   │   ├─ Form Register
│   │   │   ├─ username/email
│   │   │   └─ password
│   │   │
│   │   └─ POST /auth/register
│   │       ├─ sukses → Login
│   │       └─ gagal → Error
│   │
│   └─ Login
│       │
│       ├─ Input credential
│       └─ POST /auth/login
│           ├─ sukses
│           │   ├─ simpan JWT
│           │   └─ Task List
│           └─ gagal → Error
│
├─ TASK LIST (CORE)
│   │
│   ├─ Load Page
│   │   └─ GET /tasks
│   │       └─ filter user_id
│   │
│   ├─ Task State
│   │   ├─ active
│   │   ├─ done
│   │   └─ soft_deleted (deleted_at != null)
│   │
│   ├─ Add Task
│   │   │
│   │   ├─ Klik Add
│   │   ├─ Popup Form
│   │   │   ├─ title
│   │   │   ├─ description?
│   │   │   ├─ deadline?
│   │   │   └─ notification_time?
│   │   │
│   │   └─ POST /tasks
│   │       ├─ sukses → refresh list
│   │       └─ gagal → error
│   │
│   ├─ Toggle Done
│   │   │
│   │   └─ PATCH /tasks/:id
│   │       └─ is_done = !is_done
│   │
│   ├─ Delete Task (Soft)
│   │   │
│   │   ├─ Klik ikon sampah
│   │   ├─ Konfirmasi
│   │   └─ DELETE /tasks/:id
│   │       └─ set deleted_at = now
│   │
│   └─ (Opsional) Trash View
│       │
│       └─ Hapus Permanen
│           └─ DELETE /tasks/:id?force=true
│               └─ hard delete
│
├─ TASK LIFECYCLE
│   │
│   ├─ Created
│   ├─ Updated (toggle)
│   ├─ Soft Deleted
│   │   └─ deleted_at set
│   │
│   └─ Hard Deleted
│       ├─ manual (force=true)
│       └─ auto (30 hari)
│
├─ AUTO CLEANUP
│   │
│   ├─ Cron / Worker
│   └─ Check:
│       └─ now - deleted_at > 30 hari
│           └─ Hard Delete
│
├─ NOTIFIKASI
│   │
│   ├─ Task punya notification_time
│   ├─ Server cek waktu
│   └─ Trigger notifikasi
│       └─ (MVP: console / alert)
│
├─ SECURITY / GUARD
│   │
│   ├─ Middleware JWT
│   ├─ Inject user_id ke request
│   └─ Cek ownership task
│       └─ mismatch → 403
│
└─ TIM
    │
    ├─ Azlal → UI / Screen
    ├─ Rizki → HTML / CSS / Event UI
    ├─ Refa  → Auth / JWT / Guard
    └─ Vadlan → DB / Query / Task Lifecycle


🔵**Style Guide:** *(otw, ngantuk le)*
* Login / Register: Animasi(Press) = zoom in pop up 
                    Animasi(Hover) = (blom)  
                    Warna = (blom)
                    Letak = Pojok kanan bar navigasi
                    Logo = gak ada
                    
* Tambah Task: Animasi(Press) = zoom in pop up +  
                    Animasi(Hover) = (blom)  
                    Warna = (blom)
                    Letak = Pojok kanan bar navigasi
                    Logo = gak ada
                    
* Lihat Task List: Animasi(Press) = gak ada
                    Animasi(Hover) = 
                    Warna = (blom)
                    Letak = Pojok kanan bar navigasi
                    Logo = gak ada
                    
* Beralih Done (toggle): Animasi(Press) = zoom in pop up 
                    Animasi(Hover) = (blom)  
                    Warna = (blom)
                    Letak = Pojok kanan bar navigasi
                    Logo = gak ada
                    
* Hapus Task: Animasi(Press) = zoom in pop up 
                    Animasi(Hover) = (blom)  
                    Warna = (blom)
                    Letak = Pojok kanan bar navigasi
                    Logo = Ikon sampah
                    
* Deadline Hapus Permanent (30 Hari): Animasi(Press) = zoom in pop up 
                    Animasi(Hover) = (blom)  
                    Warna = (blom)
                    Letak = Pojok kanan bar navigasi
                    Logo = gak ada
                    
* Hapus Permanen: Animasi(Press) = zoom in pop up 
                    Animasi(Hover) = (blom)  
                    Warna = (blom)
                    Letak = Pojok kanan bar navigasi
                    Logo = gak ada
                    
* Notifikasi per task: Animasi(Press) = zoom in pop up 
                    Animasi(Hover) = (blom)  
                    Warna = (blom)
                    Letak = Pojok kanan bar navigasi
                    Logo = gak ada
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

## **FASE 3A AUTH LOGIN/REGISTER (REFA)**

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
