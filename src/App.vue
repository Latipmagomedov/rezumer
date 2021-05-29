<template>
  <div id="app">
    <router-view />
  </div>
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@100;200;300;400;500;600;700;800;900&display=swap");

$bg: #111111;
$col: #ffffff;
$blue: #1771f1;
$inpBg: #161616;
$inpCol: #ffffff;
$btnBg: #1771f1;
$btnCol: #ffffff;

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  outline: none;
}

body {
  background-color: $bg;
  color: $col;
  font-family: "Montserrat", sans-serif;
}

.container {
  width: 93%;
  max-width: 980px;
  margin: 0 auto;
}

input,
button {
  height: 50px;
  border-radius: 11px;
  font-weight: 600;
  border: none;
}

input {
  padding-left: 15px;
  background-color: $inpBg;
  color: $inpCol;
  font-size: 14px;
}

textarea {
  padding-top: 20px;
  padding-left: 15px;
  border-radius: 11px;
  background-color: $inpBg;
  color: $inpCol;
  font-size: 14px;
  font-weight: 600;
  border: none;
}

button {
  padding: 0 20px;
  background-color: $btnBg;
  color: $btnCol;
  font-size: 15px;
  cursor: pointer;
}

.btn {
  display: inline-block;
  padding: 10px 20px;
  border-radius: 11px;
  background-color: $btnBg;
  color: $btnCol;
  font-size: 15px;
  font-weight: 600;
  cursor: pointer;
}

.red-bg {
  background-color: #ff2929;
  color: #fff;
}

.blue-bg {
  background-color: #1771f1;
  color: #fff;
}

.red-col {
  color: #ff3e3e;
}
</style>
