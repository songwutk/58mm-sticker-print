<script>import Barcode from 'svelte-barcode';</script>

<style>
/* +page.svelte */
/* print in media 58mm receipt printer */
/* height of sticker is 20mm */

.content {
  width: 58mm;
  height: 20mm;
  margin: 0;
  padding: 0;
  font-size: 10px;
  font-family: "THSarabunNew", sans-serif;
  font-weight: 400;
  line-height: 1.5;
  color: #212529;
  text-align: center;
  background-color: #fff;
  background-clip: border-box;
  border: 1px solid #dee2e6;
  border-radius: 0.25rem;
}
.msg{
  /* margin-top : -10px; */
  margin-top: -10px;  
}
</style>

<!-- print code128 barcode -->
<!-- example data 
  [{"name":"ผงปรุงรสฟ้าไทย","diz":"200 กรัม","barcode":"323001","price","25.00"}]-->
<div class="content"><!-- print barcode128 value is 323001 --> 
  <Barcode
  value={'323001'}
  elementTag={'canvas'}
  options={{
    format: 'CODE128',
    width: 2,
    height: 20,
    text: '323001',
    textAlign: 'center',
    textPosition: 'bottom',
    fontSize: 8,
    background: '#ffffff',
    lineColor: '#000000',
  }}
  />
  <div class="msg">ผงปรุงรสฟ้าไทย 200 กรัม</div>
  <div >25.00 บาท</div>
</div>