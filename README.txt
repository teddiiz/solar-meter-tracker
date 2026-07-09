Solar Meter Tracker PWA v8 Ready Firebase

ไฟล์นี้ใส่ Firebase config สำหรับโปรเจกต์ solar-meter-tracker แล้ว

วิธีอัปเดต GitHub Pages:
1. แตก ZIP
2. อัปโหลดไฟล์ทั้งหมดในโฟลเดอร์นี้ทับของเดิมใน repository solar-meter-tracker
3. Commit directly to main
4. รอ GitHub Pages 1-5 นาที
5. เปิดแอป URL เดิม

สำคัญก่อนใช้งาน Google Login:
ใน Firebase Console ไปที่ Authentication > Settings > Authorized domains
เพิ่มโดเมน: teddiiz.github.io

หลังเปิดแอป:
1. ไปที่ ตั้งค่า
2. กด เข้าสู่ระบบ Google
3. ล็อกอินด้วย teddiiz3ear@gmail.com
4. ถ้ามีข้อมูลเดิมบน iPhone ให้กด “ย้ายข้อมูลในเครื่องขึ้น Cloud” หนึ่งครั้ง

Firestore Rules ที่ควรใช้:
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /users/{userId}/{document=**} {
      allow read, write: if request.auth != null && request.auth.uid == userId;
    }
  }
}
