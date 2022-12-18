# SPCN-011

# create master vm (ubuntu-22.04)

## ตั้ง VM
![image](https://user-images.githubusercontent.com/119155285/208307976-efe20aa5-0439-4dab-ad7d-7c5f60b2b11d.png)
![image](https://user-images.githubusercontent.com/119155285/208308005-9f835937-6d29-4846-8e23-deb148db047b.png)
![image](https://user-images.githubusercontent.com/119155285/208308015-c5f896b0-b43a-430a-b7b0-65c5926bac14.png)
![image](https://user-images.githubusercontent.com/119155285/208308035-9a5c4833-b46e-4b9b-9e69-0529735e7df8.png)
## ที่เหลือ Next ให้หมด
![image](https://user-images.githubusercontent.com/119155285/208308061-54730272-f077-4789-a0eb-b5d0fac28db6.png)


## ทำการเข้าตัว VM ไป set profile
![image](https://user-images.githubusercontent.com/119155285/208308259-4293e6ea-7936-44c1-9d3f-e06f6a385d3a.png)
![image](https://user-images.githubusercontent.com/119155285/208308282-15e30bfc-a277-4f3d-bdde-41403cd0115c.png)
![image](https://user-images.githubusercontent.com/119155285/208308302-91eda620-4287-49eb-8c95-39663b455405.png)
![image](https://user-images.githubusercontent.com/119155285/208308313-fc5dbf27-b083-40e4-83f9-79108fc17c3b.png)
![image](https://user-images.githubusercontent.com/119155285/208308330-656950c1-eaef-4e9a-84d0-bdc190bdfe35.png)

##  เมื่อทำทุกอย่างเสร็จ loginเข้ามาได้ จะได้หน้าตาประมาณนี้

![image](https://user-images.githubusercontent.com/119155285/208308376-3bd4ac4e-a30b-4c06-babd-cc05f5c7bf53.png)

# clone from template สร้าง vm ใหม่จำนวน 2 vm
การโคลนจะทำเหมือนกันทั้งสองอัน

![image](https://user-images.githubusercontent.com/119155285/208308428-f61e6e18-1049-4037-a8f4-cca8ec09156c.png)
![image](https://user-images.githubusercontent.com/119155285/208308457-4b0c4af8-6e8f-4169-80b9-e01c25b809bf.png)

### CODE เปลี่ยน Host Name
         sudo hostnamectl set -hostname (ตามด้วยชื่อที่จะตั้ง)
         
### CODE เปลี่ยนตั้งเวลา
            sudo timedatectl set-timezone Asia/Bangkok (เซ็ตเวลา)
            date (ดูเวลา)
            
### CODE ที่ใช้เกี่ยวกับ QEMU
              sudo apt update; sudo apt upgrade -y (อัพเดท)
              sudo apt install qemu-guest-agent (ติดตั้ง QEMU Guest Agent)
              sudo systemctl start qemu-guest-agent (เปิดการทำงาน QEMU Guest Agent)
              sudo systemctl status qemu-guest-agent (ตรวจสอบสถานะการทำงานของ QEMU Guest Agent)

### CODE ที่ใช้เปลี่ยน IP      
      ls -l /var/lib/dbus/machine-id 
      rm /var/lib/dbus/machine-id     
      nano /etc/machine-id                              //ลบข้อมูลทั้งหมดใน machine-id
      cat /etc/machine-id                               //เช็คไฟล์ machine-id 
      ln -s /etc/machine-id /var/lib/dbus/machine-id    //link ข้อมูลในไฟล์ machine-id
      ls -l /var/lib/dbus/machine-id                    //เลือกทั้งหมด
      reboot      
      
 ### summary screen    
 ![image](https://user-images.githubusercontent.com/119155285/208308777-219c26e5-d52f-4f4d-a671-4c795293e401.png)
 ![image](https://user-images.githubusercontent.com/119155285/208308801-cb1c5af1-ffbf-4835-9598-dc26fdc6f3f9.png)
 ![image](https://user-images.githubusercontent.com/119155285/208308812-17c88a3f-8c13-4220-a661-30c2a1ec0ccd.png)

### create vm from other os 
![image](https://user-images.githubusercontent.com/119155285/208308883-864b522c-9a36-4e82-9b78-e402dac9d9fb.png)
![image](https://user-images.githubusercontent.com/119155285/208308902-97d05aa7-aa84-4816-98fe-9d5ba9894c89.png)

* หน้า console ของ OS
![image](https://user-images.githubusercontent.com/119155285/208308966-340b9232-b4ef-436b-97ac-6f136b791c58.png)


** หน้า summary

![image](https://user-images.githubusercontent.com/119155285/208308983-9dd36d94-6244-4df1-8484-90b53b3b0f4c.png)

# create container template (select from CT list)

*ไปที่เมนูมุมบนขวา กด Create CT กรอกข้อมูลให้เรียบร้อย
![image](https://user-images.githubusercontent.com/119155285/208309110-b5996dbb-c340-4eb0-ab82-ef51126cca41.png)

![image](https://user-images.githubusercontent.com/119155285/208309124-36cb24e7-04b0-48d5-a889-42ea081617fa.png)

![image](https://user-images.githubusercontent.com/119155285/208309144-2fec02ad-5fc5-4f82-bc3d-4496cd4d8d47.png)

![image](https://user-images.githubusercontent.com/119155285/208309174-15f5461c-7b54-42be-8ac5-a189b771fd34.png)

*ทำการเปิด CT

![image](https://user-images.githubusercontent.com/119155285/208309217-4f4938e5-c168-4b8f-89cd-fda3e96f9032.png)

**summary ของ CT

![image](https://user-images.githubusercontent.com/119155285/208309242-3b568826-1b39-4676-bd38-087e839144e3.png)






