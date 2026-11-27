# รายงานแบบฝึกหัด Socket API & Docker (Assignment 1 & 2)

**ข้อมูลผู้จัดทำ**
* ชื่อ-นามสกุล: นาย ไชยวัฒน์ แก้วเกตุ
* รหัสนักศึกษา: 6714951024
* กลุ่ม/เซคชัน: 1

---

## แบบฝึกหัดที่ 1: ระบบ Chat ด้วย Docker (2 Clients & 1 Server)

### คำอธิบายการทำงาน
ระบบแชทนี้ประยุกต์ใช้ Socket API แบบ TCP ในการส่งข้อมูลระหว่าง Client 2 ตัว ผ่าน Server กลาง โดยรันอยู่ในรูปแบบของ Docker Multi-container และใช้ Docker Compose ในการจัดการ

### ขั้นตอนการเริ่มทำงาน (How to run)
1. เข้าไปที่โฟลเดอร์แบบฝึกหัดที่ 1:
   ```bash
   cd exercise-1
   ```
2. รันคอนเทนเนอร์ทั้งหมด:
   ```bash
   docker-compose up --build
   ```
3. เปิด Terminal ใหม่เพื่อเข้าใช้งาน Client 1:
   ```bash
   docker exec -it chat_client1 python client.py
   ```
4. เปิด Terminal ใหม่อีกอันเพื่อเข้าใช้งาน Client 2:
   ```bash
   docker exec -it chat_client2 python client.py
   ```

### ตัวอย่างผลการทำงาน
<img width="696" height="199" alt="Screenshot 2026-11-27 121153" src="https://github.com/user-attachments/assets/c4cafa82-1eb1-4601-b3df-cecd7ccde242" />
<img width="246" height="197" alt="Screenshot 2026-11-27 121217" src="https://github.com/user-attachments/assets/8c02136d-89c1-4763-b19f-1e70a636fb96" />


---

## แบบฝึกหัดที่ 2: เว็บแอปพลิเคชัน Flask และ Socket Server

### คำอธิบายการทำงาน
แอปพลิเคชันหน้าเว็บพัฒนาด้วย Flask รับข้อความผ่านการกดส่งฟอร์ม (POST Method) จากนั้น Flask จะทำหน้าที่เป็น Client ส่งข้อความนั้นต่อไปยัง Socket Server เพื่อทำการสะท้อนข้อมูลกลับ (Echo) และแสดงผลบนหน้าเว็บ

### ขั้นตอนการเริ่มทำงาน (How to run)
1. เข้าไปที่โฟลเดอร์แบบฝึกหัดที่ 2:
   ```bash
   cd exercise-2
   ```
2. รัน Docker Compose:
   ```bash
   docker-compose up --build
   ```
3. เปิดเว็บเบราว์เซอร์ไปที่ http://localhost:5000 เพื่อทดสอบส่งข้อความ

### ตัวอย่างผลการทำงาน
<img width="603" height="197" alt="Screenshot 2026-11-27 125821" src="https://github.com/user-attachments/assets/5e999076-5b42-4d7e-adf2-f96e290fdae7" />
<img width="374" height="279" alt="Screenshot 2026-11-27 125814" src="https://github.com/user-attachments/assets/403d5b01-7181-405e-af9e-55376e792401" />

---

## วิธีหยุดการทำงานและเคลียร์ Resources
ใช้คำสั่งนี้ในโฟลเดอร์ที่มีไฟล์ `docker-compose.yml`:
```bash
docker-compose down
```
