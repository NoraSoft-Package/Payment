# Monster Payment v1.1 [ Visa ]

<a href="https://ibb.co/FzZXVNB"><img src="https://i.ibb.co/FzZXVNB/visa.gif" alt="visa" border="0"></a>

## Links

```html
<link rel="stylesheet" href="payment.css" />
<script defer src="payment.js"></script>
```

## HTML

```html
<div class="container">
  <div class="card-container">
    <div class="front">
      <div class="image">
        <img src="image/chip.png" alt="" />
        <img src="image/visa.png" alt="" />
      </div>
      <div class="card-number-box">################</div>
      <div class="flexbox">
        <div class="box">
          <span>card holder</span>
          <div class="card-holder-name">full name</div>
        </div>
        <div class="box">
          <span>expires</span>
          <div class="expiration">
            <span class="exp-month">mm</span>
            <span class="exp-year">yy</span>
          </div>
        </div>
      </div>
    </div>

    <div class="back">
      <div class="stripe"></div>
      <div class="box">
        <span>cvv</span>
        <div class="cvv-box"></div>
        <img src="image/visa.png" alt="" />
      </div>
    </div>
  </div>

  <form action="">
    <div class="inputBox">
      <span>card number</span>
      <input type="text" maxlength="16" class="card-number-input" />
    </div>
    <div class="inputBox">
      <span>card holder</span>
      <input type="text" class="card-holder-input" />
    </div>
    <div class="flexbox">
      <div class="inputBox">
        <span>expiration mm</span>
        <select name="" id="" class="month-input">
          <option value="month" selected disabled>month</option>
          <option value="01">01</option>
          <option value="02">02</option>
          <option value="03">03</option>
          <option value="04">04</option>
          <option value="05">05</option>
          <option value="06">06</option>
          <option value="07">07</option>
          <option value="08">08</option>
          <option value="09">09</option>
          <option value="10">10</option>
          <option value="11">11</option>
          <option value="12">12</option>
        </select>
      </div>
      <div class="inputBox">
        <span>expiration yy</span>
        <select name="" id="" class="year-input">
          <option value="year" selected disabled>year</option>
          <option value="2021">2021</option>
          <option value="2022">2022</option>
          <option value="2023">2023</option>
          <option value="2024">2024</option>
          <option value="2025">2025</option>
          <option value="2026">2026</option>
          <option value="2027">2027</option>
          <option value="2028">2028</option>
          <option value="2029">2029</option>
          <option value="2030">2030</option>
        </select>
      </div>
      <div class="inputBox">
        <span>cvv</span>
        <input type="text" maxlength="4" class="cvv-input" />
      </div>
    </div>
    <input type="submit" value="submit" class="submit-btn" />
  </form>
</div>
```

## CSS

```css
:root {
  --main_color: blueviolet;
  --second_color: deeppink;
}

.container {
  min-height: 100vh;
  background: #eee;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-flow: column;
  padding-bottom: 60px;
}

.container form {
  background: #fff;
  border-radius: 5px;
  box-shadow: 0 10px 15px rgba(0, 0, 0, 0.1);
  padding: 20px;
  width: 600px;
  padding-top: 160px;
}

.container form .inputBox {
  margin-top: 20px;
}

.container form .inputBox span {
  display: block;
  color: #999;
  padding-bottom: 5px;
}

.container form .inputBox input,
.container form .inputBox select {
  width: 100%;
  padding: 10px;
  border-radius: 10px;
  border: 1px solid rgba(0, 0, 0, 0.3);
  color: #444;
}

.container form .flexbox {
  display: flex;
  gap: 15px;
}

.container form .flexbox .inputBox {
  flex: 1 1 150px;
}

.container form .submit-btn {
  width: 100%;
  background: linear-gradient(45deg, var(--main_color), var(--second_color));
  margin-top: 20px;
  padding: 10px;
  font-size: 20px;
  color: #fff;
  border-radius: 10px;
  cursor: pointer;
  transition: 0.2s linear;
}

.container form .submit-btn:hover {
  letter-spacing: 2px;
  opacity: 0.8;
}

.container .card-container {
  margin-bottom: -150px;
  position: relative;
  height: 250px;
  width: 400px;
}

.container .card-container .front {
  position: absolute;
  height: 100%;
  width: 100%;
  top: 0;
  left: 0;
  background: linear-gradient(45deg, var(--main_color), var(--second_color));
  border-radius: 5px;
  backface-visibility: hidden;
  box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
  padding: 20px;
  transform: perspective(1000px) rotateY(0deg);
  transition: transform 0.4s ease-out;
}

.container .card-container .front .image {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 10px;
}

.container .card-container .front .image img {
  height: 50px;
}

.container .card-container .front .card-number-box {
  padding: 30px 0;
  font-size: 22px;
  color: #fff;
}

.container .card-container .front .flexbox {
  display: flex;
}

.container .card-container .front .flexbox .box:nth-child(1) {
  margin-right: auto;
}

.container .card-container .front .flexbox .box {
  font-size: 15px;
  color: #fff;
}

.container .card-container .back {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background: linear-gradient(45deg, var(--main_color), var(--second_color));
  border-radius: 5px;
  padding: 20px 0;
  text-align: right;
  backface-visibility: hidden;
  box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
  transform: perspective(1000px) rotateY(180deg);
  transition: transform 0.4s ease-out;
}

.container .card-container .back .stripe {
  background: #000;
  width: 100%;
  margin: 10px 0;
  height: 50px;
}

.container .card-container .back .box {
  padding: 0 20px;
}

.container .card-container .back .box span {
  color: #fff;
  font-size: 15px;
}

.container .card-container .back .box .cvv-box {
  height: 50px;
  padding: 10px;
  margin-top: 5px;
  color: #333;
  background: #fff;
  border-radius: 5px;
  width: 100%;
}

.container .card-container .back .box img {
  margin-top: 30px;
  height: 30px;
}
```

## JavaScript

```js
document.querySelector(".card-number-input").oninput = () => {
  document.querySelector(".card-number-box").innerText =
    document.querySelector(".card-number-input").value;
};

document.querySelector(".card-holder-input").oninput = () => {
  document.querySelector(".card-holder-name").innerText =
    document.querySelector(".card-holder-input").value;
};

document.querySelector(".month-input").oninput = () => {
  document.querySelector(".exp-month").innerText =
    document.querySelector(".month-input").value;
};

document.querySelector(".year-input").oninput = () => {
  document.querySelector(".exp-year").innerText =
    document.querySelector(".year-input").value;
};

document.querySelector(".cvv-input").onmouseenter = () => {
  document.querySelector(".front").style.transform =
    "perspective(1000px) rotateY(-180deg)";
  document.querySelector(".back").style.transform =
    "perspective(1000px) rotateY(0deg)";
};

document.querySelector(".cvv-input").onmouseleave = () => {
  document.querySelector(".front").style.transform =
    "perspective(1000px) rotateY(0deg)";
  document.querySelector(".back").style.transform =
    "perspective(1000px) rotateY(180deg)";
};

document.querySelector(".cvv-input").oninput = () => {
  document.querySelector(".cvv-box").innerText =
    document.querySelector(".cvv-input").value;
};
```
