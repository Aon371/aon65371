<script setup>
  import{ ref } from "vue";

  const travel = ref("");
  const money = ref(0);

  const Details = ref({
    name: "",
    tel: "",
    date: "",
    time: "",
    tables: ""
  });
  
  //const travelList = ref(['Gunma','Shibuya','Akihabara','Kyoto','Fukuoka']);
  const travelList = ref([
    {name:'อินทนนท์ คาเฟ่', price:80, size: {s:80, m: 150, l: 200}, img:"https://bluemochateas.com/wp-content/uploads/2022/09/%E0%B8%84%E0%B8%B2%E0%B9%80%E0%B8%9F%E0%B9%88%E0%B9%83%E0%B8%99%E0%B8%AA%E0%B8%A7%E0%B8%99.jpg.webp" },
    {name:'บ้านต้นไม้ คาเฟ่', price: 50 , size: {s:50, m: 100, l: 150}, img:"https://bluemochateas.com/wp-content/uploads/2022/09/%E0%B8%84%E0%B8%B2%E0%B9%80%E0%B8%9F%E0%B9%88%E0%B9%80%E0%B8%A5%E0%B9%87%E0%B8%81%E0%B9%83%E0%B8%99%E0%B8%9A%E0%B9%89%E0%B8%B2%E0%B8%99%E0%B9%84%E0%B8%A1%E0%B9%89%E0%B8%81%E0%B8%A5%E0%B8%B2%E0%B8%87%E0%B8%AA%E0%B8%A7%E0%B8%99.jpg.webp" },
    {name:'Cittycat cafe', price: 90 , size: {s:90, m: 120, l: 150}, img:"https://bluemochateas.com/wp-content/uploads/2022/09/%E0%B8%95%E0%B8%81%E0%B9%81%E0%B8%95%E0%B9%88%E0%B8%87%E0%B8%AB%E0%B8%99%E0%B9%89%E0%B8%B2%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%99%E0%B8%81%E0%B8%B2%E0%B9%81%E0%B8%9F%E0%B8%94%E0%B9%89%E0%B8%A7%E0%B8%A2%E0%B8%95%E0%B9%89%E0%B8%99%E0%B9%84%E0%B8%A1%E0%B9%89.jpg.webp" },
    {name:'Paradon cafe', price: 100 , size: {s:100, m: 150, l: 200}, img:"https://bluemochateas.com/wp-content/uploads/2022/09/%E0%B8%97%E0%B8%B3%E0%B8%8B%E0%B8%B8%E0%B9%89%E0%B8%A1%E0%B8%95%E0%B9%89%E0%B8%99%E0%B9%84%E0%B8%A1%E0%B9%89%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%99%E0%B8%81%E0%B8%B2%E0%B9%81%E0%B8%9F-1152x1536.jpg.webp" },
    {name:'Green cafe', price: 30 , size: {s:30, m: 50, l: 100}, img:"https://bluemochateas.com/wp-content/uploads/2022/09/%E0%B8%97%E0%B8%B3%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%99%E0%B8%81%E0%B8%B2%E0%B9%81%E0%B8%9F%E0%B8%A3%E0%B9%88%E0%B8%A1%E0%B8%A3%E0%B8%B7%E0%B9%88%E0%B8%99%E0%B9%83%E0%B8%88%E0%B8%81%E0%B8%A5%E0%B8%B2%E0%B8%87%E0%B9%80%E0%B8%A1%E0%B8%B7%E0%B8%AD%E0%B8%87-1024x854.jpg.webp" }, 
    {name:'Blackforrest caffe', img:"https://bluemochateas.com/wp-content/uploads/2022/09/%E0%B8%9A%E0%B8%A3%E0%B8%A3%E0%B8%A2%E0%B8%B2%E0%B8%81%E0%B8%B2%E0%B8%A8%E0%B8%A3%E0%B9%89%E0%B8%B2%E0%B8%99%E0%B8%81%E0%B8%B2%E0%B9%81%E0%B8%9F%E0%B9%81%E0%B8%9A%E0%B8%9A%E0%B8%AA%E0%B8%A7%E0%B8%99-768x576.jpg.webp"}
  ]);
  
  const bookingList = ref([
  ]);

  

  function booking(restaurant, details) {

  const bookingData = {
    restaurantName: restaurant.name,
    name: details.name,
    tel: details.tel,
    date: details.date,
    time: details.time,
    tables: details.tables,
  };
  
  bookingList.value.push(bookingData);

  Details.name = '';
  Details.tel = '';
  Details.date = '';
  Details.time = '';
  Details.tables = '';
  alert("Booking Complete!!! , Please Check Your Booking Details at The bottom of page")
}

  
  
//   //function
// function booking(name){
//   //name -> bookingList []
//   bookingList.value.push(name)
// }      

</script>

<template>
  <h1 style="color: rgb(69, 33, 12) ;">จองร้านกาแฟ</h1> <br>
  <div class="container-input" style="background-color: #d49e39;">
    <h4 style="color: rgb(247, 27, 167); font-weight: bold;">** กรุณากรอกข้อมูลให้ครบถ้วนก่อนจองโต๊ะ **</h4>
    <div class="cont">
          <div class="text-input">
            Name &nbsp; <input type="text" v-model="Details.name" required> 
          </div>
          <div class="text-input">
            Tel &nbsp; <input type="tel" v-model="Details.tel" required> 
          </div>
          <div class="text-input">  
            DD/MM/YYYY &nbsp; <input type="date" v-model="Details.date" required>
          </div>
          <div class="text-input">
            Time &nbsp; <input type="time" v-model="Details.time" required>
          </div>
          <div class="text-input">
            Tables &nbsp; <input type="number" v-model="Details.tables" required> 
          </div>
    </div>
  </div>
  <div class="container text-center" style="background-color: ; border-radius: 20px;">
    <div class="row" align="center">
      <div class="col" v-for="(item, index) in travelList" :key="index">
        <div class="card" style="width: 18rem; background-color: #7993a4; margin: 25px; border-radius: 30px;">
          <img :src="item.img" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">{{ item.name }}</h5>
            <p class="card-text">Some quick example text.</p>
             <br>
            <a href="#" class="btn" @click="booking(item, Details)">จองโต๊ะ</a>
          </div>
        </div>
      </div>
    </div>
  </div> <br>
  <table class="table table-dark table-striped" v-if="bookingList.length > 0">
  <thead>
    <h4>Details</h4>
    <tr>
      <th scope="col">ชื่อร้าน</th>
      <th scope="col">ชื่อผู้จอง</th>
      <th scope="col">เบอร์โทร</th>
      <th scope="col">วัน/เดือน/ปี</th>
      <th scope="col">เวลา</th>
      <th scope="col">จำนวนโต๊ะ</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(booking, index) in bookingList" :key="index">
      <td>{{ booking.restaurantName }}</td>
      <td>{{ booking.name }}</td>
      <td>{{ booking.tel }}</td>
      <td>{{ booking.date }}</td>
      <td>{{ booking.time }}</td>
      <td>{{ booking.tables }}</td>
    </tr>
  </tbody>
</table> <br>

  <div class="color">
    <h1>ไปเที่ยวกันมั้ย....</h1>
    <input type="radio" value="a" v-model="travel" />ภูเขา
    <input type="radio" value="b" v-model="travel" />ทะเล &nbsp;
    จำนวนเงิน &nbsp;
    <input type="number" v-model="money">
    <div v-if="money < 100">อยู่บ้านนอน</div>
    <div v-else-if="money >= 100 && money < 1000000">ขึ้นรถไปเที่ยว</div>
    <div v-else-if="money >= 1000000">ขับเครื่องบินส่วนตัวไป</div>
    <div v-else-if="money <= 0">กรุณากรอกจำนวนเงิน</div>
    <div v-if="travel === 'a' ">ภาพภูเขา</div>
    <div v-else>ภาพทะเล</div>
    <br>
    <button type="button" v-if="money < 50" disabled style="background-color: rgba(255, 0, 0, 0.142);">Let's Go</button>
    <button type="button" v-else style="background-color: green;">Let's Go</button>
  </div>
</template>