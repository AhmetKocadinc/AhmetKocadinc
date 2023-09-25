- 👋 Hi, I’m @AhmetKocadinc
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
AhmetKocadinc/AhmetKocadinc is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

-- Travel database oluşturma

create database travel

-- passanger_travel adlı csv veri setinin tablosunu oluşturma
CREATE TABLE passenger (
  id integer,
  booking_id integer,
  gender VARCHAR(50),
  name VARCHAR(50),
  dateofbirth DATE,
  PRIMARY KEY (id)
)

--Passanger_travel tablosunun içeriğini csv dosyasının içerisindeki verileri çekme
COPY passenger(id, booking_id, gender, name, dateofbirth)
FROM 'C:\Program Files\PostgreSQL\15\bin\passenger_travel.csv'
DELIMITER ','
CSV HEADER;

--payment_travel tablosunu oluşturmak
CREATE TABLE payment (
  id integer,
  bookingid integer,
  amount integer,
  cardtype VARCHAR(100),
  paymentstatus VARCHAR(100),
  cardnumber VARCHAR(100),
  paymentdate date
)

--payment_travel verisetini içeri aktarma
COPY payment(id, bookingid,amount, cardtype, paymentstatus, cardnumber,paymentdate)
FROM 'C:\Program Files\PostgreSQL\15\bin\payment_travel.csv'
DELIMITER ','
CSV HEADER;


--Booking_travel tablosunu oluşturmak
CREATE TABLE booking (
  id integer,
  contactid integer,
  contactemail VARCHAR(100),
  company VARCHAR(100),
  membersales VARCHAR(100),
  userid VARCHAR(100),
  userregisterdate VARCHAR(100),
  environment VARCHAR(100),
  bookingdate date
)

--booking_travel verisetini içeri aktarma

COPY booking(id, contactid, contactemail, company, membersales,userid, userregisterdate, environment, bookingdate)
FROM 'C:\Program Files\PostgreSQL\15\bin\booking_travel.csv'
DELIMITER ','
CSV HEADER;
