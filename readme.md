<pre class="pat-markdown">
### วิธีการ Install Robotframework

     1. Download python 2.7 
        1.1 https://www.python.org/downloads/release/python-2716/
        1.2 Set Environment Path: C:\Python27
                            Path: C:\Python27\Scripts
     2. Set Environment bin (bin:chromedriver)
        2.1 chromedriver: https://sites.google.com/a/chromium.org/chromedriver/
        2.2 firefox: https://github.com/mozilla/geckodriver/releases
        2.3 สร้าง Folder bin ไว้ที่ไดรฟ์ C: และนำไฟล์ driver ที่แตก zip แล้วไปวางไว้ที่โฟลเดอร์ดังกล่าว
        2.4 ดำเนินการ set path environment เป็น C:/bin และทำการ Restart เครื่อง



### วิธีติดตั้ง Robot Framework

     1. pip install robotframework : Install
     2. robot --version : Check Version or , pybot --version
     3. pip install robotframework-seliniumlibrary : Install lib ของ seliniumlibrary




### Extension VS Code ที่ใช้สำหรับ Robot Framework

     1.- Robot Framework Intellisense
     2.- Robot framework language
     3.- Robotf-extension
     4.- robotframework
     5.- Robot Framework Helper

### Connect DB 
     Install: pip install PyMySQL (Library:)
     Install: pip install -U robotframework-databaselibrary
     ประกาศ หัว Library 
     Library           DatabaseLibrary
     Library           OperatingSystem
     *** Variable ***
${DBName}       shipping    
${DBUser}       root
${DBPass}       P@ssw0rd
${DBHost}       10.6.3.61
${DBPort}       3306
*** Keywords ***

Connect Database
    Connect To Database    pymysql    ${DBName}    ${DBUser}    ${DBPass}    ${DBHost}    ${DBPort}
    
     
### IF Else 

     Library String: pip install python-string-utils
ตัวอย่าง: (Connect To DB First)
Emp Select
    ${employee} =        Query           select username from tab_user where username = 'admin';
    ${employee} =       Convert To String           ${employee[0][0]}      
    Run Keyword IF    '${employee}'=='pupu'    Log To Console    I am in If Condition  
    ...             ELSE IF     '${employee}'=='admin'      Log To Console      ADMIN JAAAAAAAA
    ...                 ELSE    Log To Console      ไม่มีอะไรเลยยย 
หมายเหตุ: ตอน Select มาต้อง Convert To String เพื่อ Select [แถว][คอลัมน์]

### How To write Condition In IF, Else
      '${Username}'=='admin' and '${UID}'=='1' 
     ใช้ and เพื่อเชื่อม condition 


### String Should Be Equal

     *** Settings ***
     Library    String

     *** Test Cases ***
     TC
          ${str1} =   Convert To Lowercase    ABC
          ${str2} =   Convert To Lowercase    1A2c3D
          Should Be Equal    ${str1}     abc
          Should Be Equal    ${str2}     1a2c3d


### การ Echo RobotFramework

     Pring String, Variable
     สามารถใช้คำสั่ง     Log To Console      ${SQL}  เพื่อ Echo ค่าออกมาเช็คได้

</div>