🎨 Theme Preset: e-Portfolio / PA Style

คู่มือนี้สรุปเฉพาะ คลาส (Class) และ CSS สำเร็จรูป ที่คุณสามารถนำไป "คัดลอกและแปะ" ลงในโครงสร้างเว็บเดิมของคุณ (HTML, React, Vue) เพื่อให้ได้หน้าตา (Look & Feel) แบบระบบแฟ้มสะสมผลงานทันที โดยไม่กระทบกับโครงสร้างเลย์เอาต์เดิม

1. ⚙️ Global CSS (ใส่ในไฟล์ style.css หรือ index.css)

คัดลอกโค้ดนี้ไปใส่ในไฟล์ CSS หลักของคุณ เพื่อปรับฟอนต์ พื้นหลังลายตารางกราฟ และแอนิเมชันพื้นฐาน

@import url('[https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;500;600;700&display=swap](https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;500;600;700&display=swap)');

body {
  font-family: 'Sarabun', sans-serif;
  background-color: #f0f4ff;
  /* ลายตารางกราฟบางๆ */
  background-image: 
    linear-gradient(rgba(180, 200, 230, 0.3) 1px, transparent 1px),
    linear-gradient(90deg, rgba(180, 200, 230, 0.3) 1px, transparent 1px);
  background-size: 20px 20px;
}

/* แอนิเมชันเด้งขึ้นตอนโหลด */
@keyframes popIn {
  0% { transform: scale(0.95); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}
.animate-pop { 
  animation: popIn 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards; 
}

/* แอนิเมชันลอยขึ้นลง (สำหรับของตกแต่ง) */
@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-10px); }
}
.animate-float { 
  animation: float 3s ease-in-out infinite; 
}


2. 🎨 คลาสสี (Color Palette)

หากโปรเจกต์คุณใช้ Tailwind CSS สามารถกำหนดสีเหล่านี้เพื่อนำไปใช้ในโครงสร้างเดิมได้เลย หรือจะจำรหัสสี (#HEX) ไปใส่ตรงๆ ก็ได้

สีฟ้าหลัก (Primary/Header): #1e88e5

สีกรมท่า (Heading/Text Dark): #1a2b4c

สีม่วง (Action 1): #7b61ff

สีเขียวอมฟ้า (Action 2): #00bfa5

สีส้ม (Action 3): #ff9800

3. 🧩 Utility Classes (คลาสสำเร็จรูปสำหรับแปะใน Tag)

นำ String ของคลาสเหล่านี้ ไปแปะใน className="..." หรือ class="..." บนโครงสร้าง Div/Button เดิมของคุณได้เลย

📦 กล่อง (Card / Container)

เปลี่ยน Div ธรรมดาให้เป็นกล่องที่มีความโค้งมนสูงและมีเงาฟุ้งแบบ e-Portfolio

bg-white rounded-[2rem] shadow-[0_8px_30px_rgb(0,0,0,0.04)] border border-slate-100 p-6

🖱️ ปุ่มกด (Buttons)

ทรงปุ่มจะเป็นแบบวงรี (Pill) เสมอ และมีเอฟเฟกต์ยกตัวขึ้นเมื่อเอาเมาส์ชี้

ปุ่มหลัก (Primary):

bg-[#1e88e5] text-white px-6 py-2.5 rounded-full font-medium shadow-md hover:shadow-lg hover:-translate-y-1 transition-all duration-300

ปุ่มรอง (Secondary/Outline):

bg-white text-slate-700 border border-slate-200 px-6 py-2.5 rounded-full font-medium hover:bg-slate-50 hover:-translate-y-1 transition-all duration-300

✨ กล่องสไตล์กระจกโปร่งแสง (Glassmorphism)

เหมาะสำหรับนำไปใส่เป็นพื้นหลังของเมนู หรือกล่องที่วางทับบนพื้นหลังสีเข้ม (เช่น บน Header สีฟ้า)

bg-white/20 backdrop-blur-sm border border-white/10 rounded-full

🏷️ ป้ายกำกับ / แท็ก (Pills / Badges)

สำหรับแสดงสถานะ หรือหมวดหมู่เล็กๆ

inline-flex items-center gap-2 px-3 py-1 bg-blue-50 text-blue-600 rounded-full text-xs font-bold border border-blue-100

👆 เอฟเฟกต์โฮเวอร์ทั่วไป (Universal Hover)

หากมีโครงสร้างเดิมอยู่แล้ว แค่เติมคลาสชุดนี้เข้าไป โครงสร้างนั้นจะดูมีชีวิตชีวาขึ้นทันที

transition-all duration-300 hover:-translate-y-1 hover:shadow-md cursor-pointer

💡 วิธีใช้งาน (ตัวอย่างการนำไปครอบโครงสร้างเดิม):
หากคุณมี <div class="col-span-12">...เนื้อหาเดิม...</div>
เพียงแค่แก้เป็น <div class="col-span-12 bg-white rounded-[2rem] shadow-[0_8px_30px_rgb(0,0,0,0.04)] border border-slate-100 p-6">...เนื้อหาเดิม...</div> ก็จะได้สไตล์กล่องแบบ PA ทันที
