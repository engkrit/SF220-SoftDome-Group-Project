<script>
  import { mode , subjects } from './stores.js';
  function DelSubject(subject){
      alert('Completed');
      $subjects = $subjects.filter(item => subject.id != item.id)
  }
</script>
<h1>รายชื่อวิชาที่เปิดลงทะเบียน</h1>
{#each $subjects as subject}
    <div class='frame'>
      <div><strong>
        {subject.subjectName}
        {subject.id}
      </strong></div>
      <div>
        <strong>Section:</strong> {subject.section}  
      </div>
      <div>
        <strong>อาจารย์:</strong> {subject.teacher}
      </div>
      <div>
        <strong>เวลา:</strong> {subject.date}
      </div>
      <div>
        <strong>จำนวนรับ:</strong> {subject.amount}
        <strong>เหลือ:</strong> {subject.remaining}
      </div>
      <div>
        <strong>เปิดรับสมัครขอโควตา:</strong> {subject.ApplicationDate}
      </div>
      <button class = ask on:click|once={() => DelSubject(subject)}>ลบวิชานี้</button>
      </div>
{/each}
<button on:click={()=>$mode='admin'}>Back to Menu</button>
<style>
  .frame {
  background: rgba(0 , 0 ,0 ,0.1);
  color: #000000;
  border: 500px;
  border-radius: 5px;
  padding: 10px;
  margin: 5px;
}
@import url('https://fonts.googleapis.com/css2?family=Chonburi&family=Noto+Sans+Thai:wght@400;700&display=swap');

h1 {
  font-family: 'Noto Sans Thai', sans-serif;
}
  
div {
  font-family: 'Noto Sans Thai', sans-serif;
  line-height: 50px;
}
button {
  font-family: 'Noto Sans Thai', sans-serif;
  background-color: black;
  color: white;
  border-radius: 5px;
  font-family: 'Noto Sans Thai', sans-serif;
}
</style>