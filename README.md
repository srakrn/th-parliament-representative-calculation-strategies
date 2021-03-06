# โปรแกรมคำนวนจำนวนสส.บัญชีรายชื่อ

เรโพสิทอรีนี้เก็บการตีความร่างพระราชบัญญัติประกอบรัฐธรรมนูญว่าด้วยการเลือกตั้งสมาชิกสภาผู้แทนราษฎร ในส่วนของการคำนวนสส. ตามการตีความของผู้เขียนโค้ดแต่ละท่าน ต่อร่างที่นำเสนอต่างกัน

## ที่มา

รัฐสภาลงมติวพิจารณาร่างพระราชบัญญัติประกอบรัฐธรรมนูญว่าด้วยการเลือกตั้งสมาชิกสภาผู้แทนราษฎร โดยแนวทางประกอบไปด้วย 3 ร่างหลักด้วยกัน

- ร่างของคณะกรรมาธิการวิสามัญพิจารณาร่างกฎหมายลูก ฝั่งเสียงข้างมาก (ซึ่งเป็นที่รู้จักในชื่อ "ร่าง 100") เขียนแทนด้วย `100-committee`
- ร่างของพรรคก้าวไกล แปรญัตติจากร่างของคณะกรรมาธิการวิสามัญพิจารณาร่างกฎหมายลูก ฝั่งเสียงข้างมาก (ซึ่งเป็นที่รู้จักในชื่อ "ร่าง 100 ก้าวไกล") เขียนแทนด้วย `100-mfp`
- ร่างของนายแพทย์ระวี มาศฉมาดล เขียนแทนด้วย `500-ravee-m` **ซึ่งเป็นร่างที่ได้รับชนะการโหวต**

สามารถดูร่างฉบับต่างๆ ได้[ที่นี่ โดยเลือกดาวน์โหลดเอกสาร หัวข้อ 3.2](https://pis.parliament.go.th/PARWeb/doc/meeting-agenda/MeetingAgendaDetailForQRCode?meetingId=Tfh53dOEhRfoqioUzj0)

เรโพสิทอรี (repository) นี้สร้างขึ้นมาเพื่อเก็บโค้ดการตีความร่างทั้ง 3 ฉบับไว้ โดยผู้ที่สนใจสามารถฟอร์ก (fork) และเขียนโค้ดสำหรับคำนวนตามการตีความของตนเอง พร้อมเปิดคำขอรวมโค้ด (pull request) กลับมาได้

## แนะนำ

- ใช้ชื่อไฟล์ในโฟลเดอร์เป็นชื่อเล่น-สมญานามของตัวเอง
- ใช้ภาษาโปรแกรมมิ่งที่ไม่ใช่ภาษาในกลุ่ม [esoteric](https://en.wikipedia.org/wiki/Esoteric_programming_language)
- โปรแกรมควรอ่านอินพุตจากไฟล์ใน `./inputs` ได้ รายละเอียดไฟล์ดูได้จาก [README.md ของ inputs](./inputs/README.md)
- คำนวน backtest โดยอิงจำนวนสส.ในแต่ละครั้ง ไม่ยึดโยงกับเลข 500 (จำนวนสส. ทั้งหมด), 400 (จำนวนสส. แบ่งเขต) หรือ 100 (จำนวนสส. บัญชีรายชื่อ)

### การ backtest กับคะแนนเลือกตั้งย้อนหลัง

การ backtest กับคะแนนเลือกตั้งย้อนหลังอาจทำได้ลำบาก เนื่องจากจำนวนและสัดส่วนของสส.บัญชีรายชื่อ-แบ่งเขต ไม่เท่ากันในการเลือกตั้งแต่ละครั้ง

โค้ดที่เขียนควรอิงเลขจำนวนสส. (รวมถึงจำนวนสส.ตามแต่ละประเภท) ในการเลือกตั้งแต่ละครั้ง เช่น หากต้องการดูว่าจะคำนวณผลการเลือกตั้งของปี 2562 ออกมาได้เป็นอย่างไร ก็ควรจะใช้จำนวนสส. แบ่งเขตเป็น 350 คน และจำนวนสส. บัญชีรายชื่อเป็น 150 คน

## ที่มา-อ้างอิง

- คะแนนเสียงเลือกตั้ง 2562 (`./inputs/2019-general-election.csv`) มาจาก[วิกิพีเดีย](https://th.wikipedia.org/wiki/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B9%80%E0%B8%A5%E0%B8%B7%E0%B8%AD%E0%B8%81%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87%E0%B8%AA%E0%B8%A1%E0%B8%B2%E0%B8%8A%E0%B8%B4%E0%B8%81%E0%B8%AA%E0%B8%A0%E0%B8%B2%E0%B8%9C%E0%B8%B9%E0%B9%89%E0%B9%81%E0%B8%97%E0%B8%99%E0%B8%A3%E0%B8%B2%E0%B8%A9%E0%B8%8E%E0%B8%A3%E0%B9%84%E0%B8%97%E0%B8%A2%E0%B9%80%E0%B8%9B%E0%B9%87%E0%B8%99%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%97%E0%B8%B1%E0%B9%88%E0%B8%A7%E0%B9%84%E0%B8%9B_%E0%B8%9E.%E0%B8%A8._2562)