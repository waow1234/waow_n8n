# waow_n8n
วิธีใช้ไฟล์ render.yaml กับ Render (Blueprints)

1) สร้าง GitHub repository ว่าง ๆ แล้วอัปโหลดไฟล์ต่อไปนี้ไว้ที่รากโปรเจ็กต์:
   - render.yaml
   - Dockerfile

2) ไปที่ https://dashboard.render.com  > New > Blueprint
   - เชื่อมกับ GitHub แล้วเลือก repository ที่มีไฟล์ render.yaml
   - กด 'Deploy' (เลือกแผน Free ให้กับทั้ง Web Service และ Postgres)

3) ครั้งแรก Render จะ build และ start ให้ จนได้ URL เช่น:
   - https://n8n-xxxx.onrender.com

4) ตั้งค่าเพิ่มเติม (ถ้าต้องการ):
   - เปิดดู Environment ของ Service แล้วเพิ่ม
     WEBHOOK_URL=https://<โดเมนที่ได้>
   - หากต้องการเปลี่ยนรหัส Basic Auth:
     N8N_BASIC_AUTH_USER / N8N_BASIC_AUTH_PASSWORD

5) หมายเหตุ Free Plan:
   - Web Service จะ sleep ถ้าไม่มีทราฟฟิก (ปลุกได้เมื่อมีการเข้าใหม่)
   - Postgres (แผนฟรี) ใช้ได้ 30 วันแรกสำหรับงานทดสอบ/POC
