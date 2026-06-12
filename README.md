📘 Design System: e-Portfolio / PA Style

คู่มือการออกแบบ UX/UI สำหรับเว็บแอปพลิเคชันสไตล์ระบบแฟ้มสะสมผลงานบุคลากร (PA) ที่เน้นความสะอาดตา (Clean), ทันสมัย (Modern), เป็นมิตร (Friendly) และดูเป็นทางการในเวลาเดียวกัน (Professional)

1. 🎨 ชุดสี (Color Palette)

การเลือกใช้สีจะเน้นพื้นหลังที่สว่าง สบายตา และใช้สีสด (Vibrant) สำหรับปุ่มหรือจุดที่ต้องการให้ผู้ใช้สนใจ (Call to action)

สีหลัก (Primary Colors)

Primary Blue: #1e88e5 (ใช้สำหรับ Header, โลโก้, ปุ่มตกลงหลัก)

Background Blue: #f0f4ff (สีพื้นหลังสุดของเว็บไซต์)

Text Dark: #1a2b4c (สีกรมท่าเข้ม ใช้สำหรับหัวข้อหลัก/Heading)

Text Muted: slate-500 หรือ #64748b (สีเทา ใช้สำหรับเนื้อหารอง/Paragraph)

สีหมวดหมู่ / ปุ่ม Action (Action Colors)

อ้างอิงจากแถบเมนู 4 สีหลักในหน้าแรก

Purple (ม่วง): #7b61ff (หมวดหมู่ที่ 1 / บุคลากร)

Blue (ฟ้า): #1e88e5 (หมวดหมู่ที่ 2 / กลุ่มสาระฯ)

Teal (เขียวอมฟ้า): #00bfa5 (หมวดหมู่ที่ 3 / หลักฐาน)

Orange (ส้ม): #ff9800 (หมวดหมู่ที่ 4 / เกียรติบัตร)

สีรอง / สีพาสเทล (Pastel Utility)

ใช้สำหรับพื้นหลังของไอคอน หรือสถิติ (Stats box) เพื่อให้ดูไม่ทึบเกินไป

Light Blue: bg-blue-50 (#eff6ff), Border blue-100

Light Purple: bg-purple-50 (#faf5ff), Border purple-100

Light Green: bg-green-50 (#f0fdf4), Border green-100

Light Orange: bg-orange-50 (#fff7ed), Border orange-100

2. 🔤 ตัวอักษร (Typography)

Font Family: Sarabun (ดาวน์โหลดได้จาก Google Fonts)

การตั้งค่า (CSS):

@import url('[https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;500;600;700&display=swap](https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;500;600;700&display=swap)');
body { font-family: 'Sarabun', sans-serif; }


น้ำหนัก (Weights):

font-bold (700) หรือ font-extrabold (800) สำหรับ หัวข้อใหญ่สุด (H1, H2)

font-medium (500) สำหรับ ปุ่มกด หรือ แท็กกำกับ

font-normal (400) สำหรับ เนื้อหาทั่วไป

3. 📐 พื้นหลัง & เลย์เอาต์ (Background & Layout)

จุดเด่นของดีไซน์นี้คือพื้นหลังลาย "สมุดกราฟ" (Grid Pattern) ที่ทำให้ดูเชื่อมโยงกับการศึกษาหรือการทำงาน

CSS สำหรับสร้างลายตารางกราฟ:

body {
  background-color: #f0f4ff;
  background-image: 
    linear-gradient(rgba(180, 200, 230, 0.3) 1px, transparent 1px),
    linear-gradient(90deg, rgba(180, 200, 230, 0.3) 1px, transparent 1px);
  background-size: 20px 20px;
}


Layout Container:

เนื้อหาหลักควรอยู่ตรงกลางหน้าจอ และจำกัดความกว้าง

Tailwind: max-w-6xl mx-auto px-4 (ประมาณ 1152px)

4. 📦 องค์ประกอบ UI (UI Components)

4.1 กล่องเนื้อหา (Cards & Containers)

ดีไซน์นี้ใช้กล่องสีขาวที่มี "ความโค้งมนสูงมาก" และ "เงาฟุ้งแบบนุ่มนวล"

คลาส Tailwind ที่ใช้บ่อย:
bg-white rounded-[2rem] shadow-[0_8px_30px_rgb(0,0,0,0.04)] border border-slate-100 p-8

คำอธิบาย:

rounded-[2rem]: ขอบมนขนาด 32px (มนกว่า rounded-3xl เล็กน้อย) ทำให้ดูเป็นมิตร

shadow-[0_8px_30px_rgb(0,0,0,0.04)]: เงาที่กระจายตัวกว้างมากแต่อ่อนมาก (Opacity 4%) ทำให้กล่องดูลอยขึ้นมาจากพื้นหลังแบบเนียนตา

border border-slate-100: ขอบสีเทาอ่อนมากบางๆ 1px เพื่อตัดขอบกล่องให้ชัดขึ้นเมื่ออยู่บนสีขาวด้วยกัน

4.2 ปุ่มกด (Buttons)

ทรงปุ่มเป็นแบบ "แคปซูล" (Pill-shape) เสมอ

Primary Button (ปุ่มหลักสีทึบ):
bg-[#1e88e5] text-white px-6 py-2.5 rounded-full font-bold shadow-md hover:-translate-y-1 transition

Secondary / Outline Button (ปุ่มรอง):
bg-white text-slate-700 border-2 border-slate-200 px-6 py-2.5 rounded-full font-bold hover:bg-slate-50 hover:-translate-y-1 transition

4.3 แถบเมนูด้านบน (Header / Navbar)

ยึดติดด้านบนสุด (sticky top-0)

พื้นหลังสีน้ำเงินหลัก

Tailwind: bg-[#1e88e5] text-white py-3 px-6 shadow-md w-full

ปุ่มย่อยใน Header ใช้แบบโปร่งแสง: bg-white/20 hover:bg-white/30 backdrop-blur-sm rounded-full

4.4 กล่องสถิติขนาดเล็ก (Stats Boxes)

อ้างอิงจากมุมขวาบนของหน้าแรก

โครงสร้าง: พื้นหลังพาสเทลจางๆ -> ไอคอนอยู่บนพื้นหลังพาสเทลเข้มขึ้นอีกนิด -> ตัวเลขขนาดใหญ่ -> คำอธิบาย

Tailwind:

<div className="bg-blue-50/50 p-5 rounded-2xl border border-blue-100">
   <div className="bg-blue-100 w-10 h-10 rounded-full flex items-center justify-center mb-3 text-blue-600">
      <Icon />
   </div>
   <div className="text-2xl font-black text-slate-800">2</div>
   <div className="text-sm text-slate-500 font-medium">บุคลากร</div>
</div>


5. ✨ เอฟเฟกต์ & แอนิเมชัน (Effects & Animations)

เพิ่มชีวิตชีวาให้ UI แบบไม่รกสายตา

Hover Effect บนการ์ด/ปุ่ม:

ใส่คลาส hover:-translate-y-1 transition duration-300 เมื่อเอาเมาส์ชี้ การ์ดจะลอยขึ้น 4px อย่างนุ่มนวล

สำหรับกล่อง 4 สีหลัก ให้เพิ่ม hover:shadow-lg เพื่อให้เงาชัดขึ้นตอนลอย

Pop-in Animation (ตอนโหลดหน้าเว็บ):

@keyframes popIn {
  0% { transform: scale(0.95); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}
.animate-pop { animation: popIn 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275) forwards; }


วิธีใช้: ใส่คลาส animate-pop ไว้ที่ Container หลักของหน้านั้นๆ

6. 📝 องค์ประกอบตกแต่งเพิ่มเติม (Decorations)

Blobs (วงแสงฟุ้งๆ): สังเกตในรูปจะมีแสงสีรุ้งฟุ้งอยู่ด้านหลังเนื้อหาบางส่วน

วิธีสร้าง (CSS/Tailwind): นำ div ทรงกลม ใส่สี และใช้ blur

  <div className="absolute top-0 right-0 w-64 h-64 bg-blue-500/10 rounded-full blur-3xl z-0"></div>


Tags (ป้ายกำกับ): ป้ายเล็กๆ สไตล์ "Public View"

Tailwind: inline-flex items-center gap-2 px-3 py-1 bg-blue-50 text-blue-600 rounded-full text-xs font-bold border border-blue-100

นำ Guideline นี้ไปประยุกต์ใช้กับ React + Tailwind CSS โปรเจกต์ใดก็ได้ รับรองว่าจะได้ UI ที่ตรงตาม Reference 100% ครับ
