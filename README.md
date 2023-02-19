# BlynkServer_in_Termux

วิธีทำ
ขั้นแรกโหลดแอพ Termux จากเว็บนี้ครับ 
https://f-droid.org/packages/com.termux/
จากนั้นเข้าไปในแอพ แล้วพิมพ์ที่ละคำสั่งตามนี้เลยครับ
(ขั้นตอนหลังจากนี้ หากว่ามีการถามให้ยืนยัน สามารถทำได้โดยกด enter ที่แป้นพิมพ์ครับ)

apt update
apt upgrade
pkg upgrade
pkg install wget
pkg install tsu
pkg intall proot
pkg install openssl-tool
wget https://raw.githubusercontent.com/MasterDevX/java/master/installjava && bash installjava
wget "https://github.com/Peterkn2001/blynk-server/releases/download/v0.41.16/server-0.41.16-java8.jar"
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout key.key -out cert.crt
nano server.properties  --> เมื่อถึงขั้นตอนนี้หน้าต่างแอพจะต่างออกไป ซึ่งให้กรอกข้อมูลตามนี้ครับ
--------(ขีดไม่เกี่ยว)
server.ssl.cert = cert.crt
server.ssl.key = key.key
server.ssl.key.pass =
data.folder = datafolder/
--------(ขีดไม่เกี่ยว)
เมื่อกรอกข้อมูล 4 บรรทัดบนนั้นเสร็จ ให้กด Ctrl + o เพื่อบันทึก และ Ctrl + x เพื่อออกจาก nano editor และจากนั้นให้พิมพ์คำสั่ง
proot -0 
จากนั้นให้พิมพ์คำสั่ง "java -version" ซึ่งจะแสดงเวอร์ชั่นจาวาของเรา จากนั้นให้พิมพ์คำสั่งนี้ครับ
java -jar server-0.41.16-java8.jar dataFolder datafolder
