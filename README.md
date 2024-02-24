<style>
  @import url(https://fonts.googleapis.com/css?family=Open+Sans:700,300);
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed,
figure, figcaption, footer, header, hgroup,
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
  margin: 0;
  padding: 0;
  border: 0;
  font: inherit;
  font-size: 100%;
  vertical-align: baseline;
}

html {
  line-height: 1;
}

ol, ul {
  list-style: none;
}

table {
  border-collapse: collapse;
  border-spacing: 0;
}

caption, th, td {
  text-align: left;
  font-weight: normal;
  vertical-align: middle;
}

q, blockquote {
  quotes: none;
}
q:before, q:after, blockquote:before, blockquote:after {
  content: "";
  content: none;
}

a img {
  border: none;
}

article, aside, details, figcaption, figure, footer, header, hgroup, main, menu, nav, section, summary {
  display: block;
}

body {
  font-family: 'Open Sans', sans-serif;
  font-size: 16px;
  font-weight: 300;
  line-height: 1em;
  text-align: center;
  color: #444;
  background: #d0d0d0;
}

h1 {
  font-size: 2.5em;
  margin: 2em 0 .5em;
}

h2 {
  margin-bottom: 3em;
}

em,
strong {
  font-weight: 700;
}

input {
  display: none;
}

article,
section {
  position: relative;
  display: block;
  margin-bottom: 2em;
  padding: 0;
}
article:not(section):last-of-type,
section:not(section):last-of-type {
  margin-bottom: 0;
}

p {
  line-height: 1.5em;
  max-width: 20em;
  margin: 1.5em auto 2em;
  padding-bottom: 2em;
}
p span {
  display: block;
}

.content {
  position: absolute;
  overflow: hidden;
  width: 100%;
  margin: 5em auto 0;
}
.content article {
  transition: transform .3s ease-in-out;
  transform: translateX(100%);
}
.content article p {
  border-bottom: 1px dotted #444;
}
.content article label {
  display: inline-block;
  margin-bottom: 3em;
}
.content article label input {
  display: inline-block;
}

.container {
  z-index: 1;
  display: flex;
  overflow: hidden;
  flex-direction: column;
  justify-content: center;
}

/*
*
*
START // CHART'S RULES
 -> "if you're picking code, don't forget the variables :)"
*/
.chart {
  font-size: 1.8em;
  display: flex;
  flex-direction: row;
  height: 12em;
  justify-content: center;
  perspective: 1000px;
  perspective-origin: 50% 50%;
}

.bar {
  font-size: 1em;
  position: relative;
  width: 2em;
  padding: 1em;
  transition: transform 2s linear;
  transform: rotateX(-30deg) rotateY(-135deg);
  transform-style: preserve-3d;
}
.bar.red .face.floor {
  background-color: rgba(185, 0, 110, 0.2);
}
.bar.red .face > .growing-bar {
  background-color: rgba(236, 0, 140, 0.8);
}
.bar.red .face > .growing-bar:before {
  color: #530031;
  border-top-color: #b9006e;
}
.bar.cyan .face.floor {
  background-color: rgba(39, 187, 241, 0.2);
}
.bar.cyan .face > .growing-bar {
  background-color: rgba(87, 202, 244, 0.8);
}
.bar.cyan .face > .growing-bar:before {
  color: #0b7da7;
  border-top-color: #27bbf1;
}
.bar.navy .face.floor {
  background-color: rgba(6, 36, 58, 0.2);
}
.bar.navy .face > .growing-bar {
  background-color: rgba(10, 64, 105, 0.8);
}
.bar.navy .face > .growing-bar:before {
  color: black;
  border-top-color: #06243a;
}
.bar.lightGray .face.floor {
  background-color: rgba(119, 119, 119, 0.2);
}
.bar.lightGray .face > .growing-bar {
  background-color: rgba(145, 145, 145, 0.8);
}
.bar.lightGray .face > .growing-bar:before {
  color: #444444;
  border-top-color: #777777;
}
.bar.yellow .face.floor {
  background-color: rgba(194, 157, 11, 0.2);
}
.bar.yellow .face > .growing-bar {
  background-color: rgba(241, 196, 15, 0.8);
}
.bar.yellow .face > .growing-bar:before {
  color: #614f06;
  border-top-color: #c29d0b;
}
.bar.lime .face.floor {
  background-color: rgba(88, 150, 0, 0.2);
}
.bar.lime .face > .growing-bar {
  background-color: rgba(118, 201, 0, 0.8);
}
.bar.lime .face > .growing-bar:before {
  color: #1c3000;
  border-top-color: #589600;
}
.bar.gray .face.floor {
  background-color: rgba(43, 43, 43, 0.2);
}
.bar.gray .face > .growing-bar {
  background-color: rgba(68, 68, 68, 0.8);
}
.bar.gray .face > .growing-bar:before {
  color: black;
  border-top-color: #2b2b2b;
}
.bar .face {
  position: relative;
  bottom: 0;
  width: 2em;
  height: 2em;
  background-position: center center;
}
.bar .side-0,
.bar .side-1 {
  overflow: hidden;
  height: 10em;
}
.bar .side-0 {
  transform: rotateY(90deg) translateZ(1em);
  background-color: rgba(241, 241, 241, 0.8);
}
.bar .side-0 .growing-bar {
  background-color: #57caf4;
}
.bar .side-1 {
  transform: rotateY(180deg) translateY(-10em) translateZ(1em);
  background-color: rgba(216, 216, 216, 0.8);
}
.bar .side-1 .growing-bar {
  background-color: #10b3ef;
}
.bar .top {
  transform: rotateX(90deg) translateZ(21em);
  text-align: center;
  background-color: rgba(254, 254, 254, 0.8);
}
.bar .floor {
  transform: rotateX(-90deg) translateY(0em) translateZ(-13em) rotate(180deg);
  text-align: center;
  background-color: transparent;
  box-shadow: 0 0 0.6em rgba(0, 0, 0, 0.3), 0.6em -1em 3em rgba(0, 0, 0, 0.3), 1em 1em 10em rgba(254, 254, 254, 0.8);
}
.bar .growing-bar {
  display: inline-block;
  width: 100%;
  height: 100%;
  transition: all .3s ease-in-out;
  transform: translateY(100%);
  opacity: 0;
}
.bar .growing-bar:before {
  font-family: 'Open Sans', sans-serif;
  font-size: .6em;
  font-weight: 700;
  display: inline-block;
  box-sizing: content-box;
  padding: .8em;
  text-align: center;
  opacity: 1;
  color: #0a4069;
  border-top: 2px dotted #0a4069;
}

.small-font-size {
  font-size: 1em;
}

.reglar-font-size {
  font-size: 1.5em;
}

.big-font-size {
  font-size: 1.8em;
}

.chart .bar-100 .face.side-0 .growing-bar,
.chart .bar-100 .face.side-1 .growing-bar {
  transform: translateY(0%);
  opacity: .8;
}
.chart .bar-100 .face.side-0 .growing-bar:before,
.chart .bar-100 .face.side-1 .growing-bar:before {
  content: "100";
}

.chart .bar-99 .face.side-0 .growing-bar,
.chart .bar-99 .face.side-1 .growing-bar {
  transform: translateY(1%);
  opacity: .8;
}
.chart .bar-99 .face.side-0 .growing-bar:before,
.chart .bar-99 .face.side-1 .growing-bar:before {
  content: "99";
}

.chart .bar-98 .face.side-0 .growing-bar,
.chart .bar-98 .face.side-1 .growing-bar {
  transform: translateY(2%);
  opacity: .8;
}
.chart .bar-98 .face.side-0 .growing-bar:before,
.chart .bar-98 .face.side-1 .growing-bar:before {
  content: "98";
}

.chart .bar-97 .face.side-0 .growing-bar,
.chart .bar-97 .face.side-1 .growing-bar {
  transform: translateY(3%);
  opacity: .8;
}
.chart .bar-97 .face.side-0 .growing-bar:before,
.chart .bar-97 .face.side-1 .growing-bar:before {
  content: "97";
}

.chart .bar-96 .face.side-0 .growing-bar,
.chart .bar-96 .face.side-1 .growing-bar {
  transform: translateY(4%);
  opacity: .8;
}
.chart .bar-96 .face.side-0 .growing-bar:before,
.chart .bar-96 .face.side-1 .growing-bar:before {
  content: "96";
}

.chart .bar-95 .face.side-0 .growing-bar,
.chart .bar-95 .face.side-1 .growing-bar {
  transform: translateY(5%);
  opacity: .8;
}
.chart .bar-95 .face.side-0 .growing-bar:before,
.chart .bar-95 .face.side-1 .growing-bar:before {
  content: "95";
}

.chart .bar-94 .face.side-0 .growing-bar,
.chart .bar-94 .face.side-1 .growing-bar {
  transform: translateY(6%);
  opacity: .8;
}
.chart .bar-94 .face.side-0 .growing-bar:before,
.chart .bar-94 .face.side-1 .growing-bar:before {
  content: "94";
}

.chart .bar-93 .face.side-0 .growing-bar,
.chart .bar-93 .face.side-1 .growing-bar {
  transform: translateY(7%);
  opacity: .8;
}
.chart .bar-93 .face.side-0 .growing-bar:before,
.chart .bar-93 .face.side-1 .growing-bar:before {
  content: "93";
}

.chart .bar-92 .face.side-0 .growing-bar,
.chart .bar-92 .face.side-1 .growing-bar {
  transform: translateY(8%);
  opacity: .8;
}
.chart .bar-92 .face.side-0 .growing-bar:before,
.chart .bar-92 .face.side-1 .growing-bar:before {
  content: "92";
}

.chart .bar-91 .face.side-0 .growing-bar,
.chart .bar-91 .face.side-1 .growing-bar {
  transform: translateY(9%);
  opacity: .8;
}
.chart .bar-91 .face.side-0 .growing-bar:before,
.chart .bar-91 .face.side-1 .growing-bar:before {
  content: "91";
}

.chart .bar-90 .face.side-0 .growing-bar,
.chart .bar-90 .face.side-1 .growing-bar {
  transform: translateY(10%);
  opacity: .8;
}
.chart .bar-90 .face.side-0 .growing-bar:before,
.chart .bar-90 .face.side-1 .growing-bar:before {
  content: "90";
}

.chart .bar-89 .face.side-0 .growing-bar,
.chart .bar-89 .face.side-1 .growing-bar {
  transform: translateY(11%);
  opacity: .8;
}
.chart .bar-89 .face.side-0 .growing-bar:before,
.chart .bar-89 .face.side-1 .growing-bar:before {
  content: "89";
}

.chart .bar-88 .face.side-0 .growing-bar,
.chart .bar-88 .face.side-1 .growing-bar {
  transform: translateY(12%);
  opacity: .8;
}
.chart .bar-88 .face.side-0 .growing-bar:before,
.chart .bar-88 .face.side-1 .growing-bar:before {
  content: "88";
}

.chart .bar-87 .face.side-0 .growing-bar,
.chart .bar-87 .face.side-1 .growing-bar {
  transform: translateY(13%);
  opacity: .8;
}
.chart .bar-87 .face.side-0 .growing-bar:before,
.chart .bar-87 .face.side-1 .growing-bar:before {
  content: "87";
}

.chart .bar-86 .face.side-0 .growing-bar,
.chart .bar-86 .face.side-1 .growing-bar {
  transform: translateY(14%);
  opacity: .8;
}
.chart .bar-86 .face.side-0 .growing-bar:before,
.chart .bar-86 .face.side-1 .growing-bar:before {
  content: "86";
}

.chart .bar-85 .face.side-0 .growing-bar, input[name='status']:checked + .content article .chart .bar.bar-3 .face.side-0 .growing-bar,
.chart .bar-85 .face.side-1 .growing-bar,
input[name='status']:checked + .content article .chart .bar.bar-3 .face.side-1 .growing-bar {
  transform: translateY(15%);
  opacity: .8;
}
.chart .bar-85 .face.side-0 .growing-bar:before, input[name='status']:checked + .content article .chart .bar.bar-3 .face.side-0 .growing-bar:before,
.chart .bar-85 .face.side-1 .growing-bar:before,
input[name='status']:checked + .content article .chart .bar.bar-3 .face.side-1 .growing-bar:before {
  content: "85";
}

.chart .bar-84 .face.side-0 .growing-bar,
.chart .bar-84 .face.side-1 .growing-bar {
  transform: translateY(16%);
  opacity: .8;
}
.chart .bar-84 .face.side-0 .growing-bar:before,
.chart .bar-84 .face.side-1 .growing-bar:before {
  content: "84";
}

.chart .bar-83 .face.side-0 .growing-bar,
.chart .bar-83 .face.side-1 .growing-bar {
  transform: translateY(17%);
  opacity: .8;
}
.chart .bar-83 .face.side-0 .growing-bar:before,
.chart .bar-83 .face.side-1 .growing-bar:before {
  content: "83";
}

.chart .bar-82 .face.side-0 .growing-bar,
.chart .bar-82 .face.side-1 .growing-bar {
  transform: translateY(18%);
  opacity: .8;
}
.chart .bar-82 .face.side-0 .growing-bar:before,
.chart .bar-82 .face.side-1 .growing-bar:before {
  content: "82";
}

.chart .bar-81 .face.side-0 .growing-bar,
.chart .bar-81 .face.side-1 .growing-bar {
  transform: translateY(19%);
  opacity: .8;
}
.chart .bar-81 .face.side-0 .growing-bar:before,
.chart .bar-81 .face.side-1 .growing-bar:before {
  content: "81";
}

.chart .bar-80 .face.side-0 .growing-bar,
.chart .bar-80 .face.side-1 .growing-bar {
  transform: translateY(20%);
  opacity: .8;
}
.chart .bar-80 .face.side-0 .growing-bar:before,
.chart .bar-80 .face.side-1 .growing-bar:before {
  content: "80";
}

.chart .bar-79 .face.side-0 .growing-bar,
.chart .bar-79 .face.side-1 .growing-bar {
  transform: translateY(21%);
  opacity: .8;
}
.chart .bar-79 .face.side-0 .growing-bar:before,
.chart .bar-79 .face.side-1 .growing-bar:before {
  content: "79";
}

.chart .bar-78 .face.side-0 .growing-bar,
.chart .bar-78 .face.side-1 .growing-bar {
  transform: translateY(22%);
  opacity: .8;
}
.chart .bar-78 .face.side-0 .growing-bar:before,
.chart .bar-78 .face.side-1 .growing-bar:before {
  content: "78";
}

.chart .bar-77 .face.side-0 .growing-bar,
.chart .bar-77 .face.side-1 .growing-bar {
  transform: translateY(23%);
  opacity: .8;
}
.chart .bar-77 .face.side-0 .growing-bar:before,
.chart .bar-77 .face.side-1 .growing-bar:before {
  content: "77";
}

.chart .bar-76 .face.side-0 .growing-bar,
.chart .bar-76 .face.side-1 .growing-bar {
  transform: translateY(24%);
  opacity: .8;
}
.chart .bar-76 .face.side-0 .growing-bar:before,
.chart .bar-76 .face.side-1 .growing-bar:before {
  content: "76";
}

.chart .bar-75 .face.side-0 .growing-bar, input[name='status']:checked + .content article .chart .bar.bar-0 .face.side-0 .growing-bar,
.chart .bar-75 .face.side-1 .growing-bar,
input[name='status']:checked + .content article .chart .bar.bar-0 .face.side-1 .growing-bar {
  transform: translateY(25%);
  opacity: .8;
}
.chart .bar-75 .face.side-0 .growing-bar:before, input[name='status']:checked + .content article .chart .bar.bar-0 .face.side-0 .growing-bar:before,
.chart .bar-75 .face.side-1 .growing-bar:before,
input[name='status']:checked + .content article .chart .bar.bar-0 .face.side-1 .growing-bar:before {
  content: "75";
}

.chart .bar-74 .face.side-0 .growing-bar,
.chart .bar-74 .face.side-1 .growing-bar {
  transform: translateY(26%);
  opacity: .8;
}
.chart .bar-74 .face.side-0 .growing-bar:before,
.chart .bar-74 .face.side-1 .growing-bar:before {
  content: "74";
}

.chart .bar-73 .face.side-0 .growing-bar,
.chart .bar-73 .face.side-1 .growing-bar {
  transform: translateY(27%);
  opacity: .8;
}
.chart .bar-73 .face.side-0 .growing-bar:before,
.chart .bar-73 .face.side-1 .growing-bar:before {
  content: "73";
}

.chart .bar-72 .face.side-0 .growing-bar,
.chart .bar-72 .face.side-1 .growing-bar {
  transform: translateY(28%);
  opacity: .8;
}
.chart .bar-72 .face.side-0 .growing-bar:before,
.chart .bar-72 .face.side-1 .growing-bar:before {
  content: "72";
}

.chart .bar-71 .face.side-0 .growing-bar,
.chart .bar-71 .face.side-1 .growing-bar {
  transform: translateY(29%);
  opacity: .8;
}
.chart .bar-71 .face.side-0 .growing-bar:before,
.chart .bar-71 .face.side-1 .growing-bar:before {
  content: "71";
}

.chart .bar-70 .face.side-0 .growing-bar,
.chart .bar-70 .face.side-1 .growing-bar {
  transform: translateY(30%);
  opacity: .8;
}
.chart .bar-70 .face.side-0 .growing-bar:before,
.chart .bar-70 .face.side-1 .growing-bar:before {
  content: "70";
}

.chart .bar-69 .face.side-0 .growing-bar,
.chart .bar-69 .face.side-1 .growing-bar {
  transform: translateY(31%);
  opacity: .8;
}
.chart .bar-69 .face.side-0 .growing-bar:before,
.chart .bar-69 .face.side-1 .growing-bar:before {
  content: "69";
}

.chart .bar-68 .face.side-0 .growing-bar,
.chart .bar-68 .face.side-1 .growing-bar {
  transform: translateY(32%);
  opacity: .8;
}
.chart .bar-68 .face.side-0 .growing-bar:before,
.chart .bar-68 .face.side-1 .growing-bar:before {
  content: "68";
}

.chart .bar-67 .face.side-0 .growing-bar,
.chart .bar-67 .face.side-1 .growing-bar {
  transform: translateY(33%);
  opacity: .8;
}
.chart .bar-67 .face.side-0 .growing-bar:before,
.chart .bar-67 .face.side-1 .growing-bar:before {
  content: "67";
}

.chart .bar-66 .face.side-0 .growing-bar,
.chart .bar-66 .face.side-1 .growing-bar {
  transform: translateY(34%);
  opacity: .8;
}
.chart .bar-66 .face.side-0 .growing-bar:before,
.chart .bar-66 .face.side-1 .growing-bar:before {
  content: "66";
}

.chart .bar-65 .face.side-0 .growing-bar,
.chart .bar-65 .face.side-1 .growing-bar {
  transform: translateY(35%);
  opacity: .8;
}
.chart .bar-65 .face.side-0 .growing-bar:before,
.chart .bar-65 .face.side-1 .growing-bar:before {
  content: "65";
}

.chart .bar-64 .face.side-0 .growing-bar,
.chart .bar-64 .face.side-1 .growing-bar {
  transform: translateY(36%);
  opacity: .8;
}
.chart .bar-64 .face.side-0 .growing-bar:before,
.chart .bar-64 .face.side-1 .growing-bar:before {
  content: "64";
}

.chart .bar-63 .face.side-0 .growing-bar,
.chart .bar-63 .face.side-1 .growing-bar {
  transform: translateY(37%);
  opacity: .8;
}
.chart .bar-63 .face.side-0 .growing-bar:before,
.chart .bar-63 .face.side-1 .growing-bar:before {
  content: "63";
}

.chart .bar-62 .face.side-0 .growing-bar,
.chart .bar-62 .face.side-1 .growing-bar {
  transform: translateY(38%);
  opacity: .8;
}
.chart .bar-62 .face.side-0 .growing-bar:before,
.chart .bar-62 .face.side-1 .growing-bar:before {
  content: "62";
}

.chart .bar-61 .face.side-0 .growing-bar,
.chart .bar-61 .face.side-1 .growing-bar {
  transform: translateY(39%);
  opacity: .8;
}
.chart .bar-61 .face.side-0 .growing-bar:before,
.chart .bar-61 .face.side-1 .growing-bar:before {
  content: "61";
}

.chart .bar-60 .face.side-0 .growing-bar,
.chart .bar-60 .face.side-1 .growing-bar {
  transform: translateY(40%);
  opacity: .8;
}
.chart .bar-60 .face.side-0 .growing-bar:before,
.chart .bar-60 .face.side-1 .growing-bar:before {
  content: "60";
}

.chart .bar-59 .face.side-0 .growing-bar,
.chart .bar-59 .face.side-1 .growing-bar {
  transform: translateY(41%);
  opacity: .8;
}
.chart .bar-59 .face.side-0 .growing-bar:before,
.chart .bar-59 .face.side-1 .growing-bar:before {
  content: "59";
}

.chart .bar-58 .face.side-0 .growing-bar,
.chart .bar-58 .face.side-1 .growing-bar {
  transform: translateY(42%);
  opacity: .8;
}
.chart .bar-58 .face.side-0 .growing-bar:before,
.chart .bar-58 .face.side-1 .growing-bar:before {
  content: "58";
}

.chart .bar-57 .face.side-0 .growing-bar,
.chart .bar-57 .face.side-1 .growing-bar {
  transform: translateY(43%);
  opacity: .8;
}
.chart .bar-57 .face.side-0 .growing-bar:before,
.chart .bar-57 .face.side-1 .growing-bar:before {
  content: "57";
}

.chart .bar-56 .face.side-0 .growing-bar,
.chart .bar-56 .face.side-1 .growing-bar {
  transform: translateY(44%);
  opacity: .8;
}
.chart .bar-56 .face.side-0 .growing-bar:before,
.chart .bar-56 .face.side-1 .growing-bar:before {
  content: "56";
}

.chart .bar-55 .face.side-0 .growing-bar, input[name='status']:checked + .content article .chart .bar.bar-1-1 .face.side-0 .growing-bar,
.chart .bar-55 .face.side-1 .growing-bar,
input[name='status']:checked + .content article .chart .bar.bar-1-1 .face.side-1 .growing-bar {
  transform: translateY(45%);
  opacity: .8;
}
.chart .bar-55 .face.side-0 .growing-bar:before, input[name='status']:checked + .content article .chart .bar.bar-1-1 .face.side-0 .growing-bar:before,
.chart .bar-55 .face.side-1 .growing-bar:before,
input[name='status']:checked + .content article .chart .bar.bar-1-1 .face.side-1 .growing-bar:before {
  content: "55";
}

.chart .bar-54 .face.side-0 .growing-bar,
.chart .bar-54 .face.side-1 .growing-bar {
  transform: translateY(46%);
  opacity: .8;
}
.chart .bar-54 .face.side-0 .growing-bar:before,
.chart .bar-54 .face.side-1 .growing-bar:before {
  content: "54";
}

.chart .bar-53 .face.side-0 .growing-bar,
.chart .bar-53 .face.side-1 .growing-bar {
  transform: translateY(47%);
  opacity: .8;
}
.chart .bar-53 .face.side-0 .growing-bar:before,
.chart .bar-53 .face.side-1 .growing-bar:before {
  content: "53";
}

.chart .bar-52 .face.side-0 .growing-bar,
.chart .bar-52 .face.side-1 .growing-bar {
  transform: translateY(48%);
  opacity: .8;
}
.chart .bar-52 .face.side-0 .growing-bar:before,
.chart .bar-52 .face.side-1 .growing-bar:before {
  content: "52";
}

.chart .bar-51 .face.side-0 .growing-bar,
.chart .bar-51 .face.side-1 .growing-bar {
  transform: translateY(49%);
  opacity: .8;
}
.chart .bar-51 .face.side-0 .growing-bar:before,
.chart .bar-51 .face.side-1 .growing-bar:before {
  content: "51";
}

.chart .bar-50 .face.side-0 .growing-bar,
.chart .bar-50 .face.side-1 .growing-bar {
  transform: translateY(50%);
  opacity: .8;
}
.chart .bar-50 .face.side-0 .growing-bar:before,
.chart .bar-50 .face.side-1 .growing-bar:before {
  content: "50";
}

.chart .bar-49 .face.side-0 .growing-bar,
.chart .bar-49 .face.side-1 .growing-bar {
  transform: translateY(51%);
  opacity: .8;
}
.chart .bar-49 .face.side-0 .growing-bar:before,
.chart .bar-49 .face.side-1 .growing-bar:before {
  content: "49";
}

.chart .bar-48 .face.side-0 .growing-bar,
.chart .bar-48 .face.side-1 .growing-bar {
  transform: translateY(52%);
  opacity: .8;
}
.chart .bar-48 .face.side-0 .growing-bar:before,
.chart .bar-48 .face.side-1 .growing-bar:before {
  content: "48";
}

.chart .bar-47 .face.side-0 .growing-bar,
.chart .bar-47 .face.side-1 .growing-bar {
  transform: translateY(53%);
  opacity: .8;
}
.chart .bar-47 .face.side-0 .growing-bar:before,
.chart .bar-47 .face.side-1 .growing-bar:before {
  content: "47";
}

.chart .bar-46 .face.side-0 .growing-bar,
.chart .bar-46 .face.side-1 .growing-bar {
  transform: translateY(54%);
  opacity: .8;
}
.chart .bar-46 .face.side-0 .growing-bar:before,
.chart .bar-46 .face.side-1 .growing-bar:before {
  content: "46";
}

.chart .bar-45 .face.side-0 .growing-bar, input[name='status']:checked + .content article .chart .bar.bar-2 .face.side-0 .growing-bar,
.chart .bar-45 .face.side-1 .growing-bar,
input[name='status']:checked + .content article .chart .bar.bar-2 .face.side-1 .growing-bar {
  transform: translateY(55%);
  opacity: .8;
}
.chart .bar-45 .face.side-0 .growing-bar:before, input[name='status']:checked + .content article .chart .bar.bar-2 .face.side-0 .growing-bar:before,
.chart .bar-45 .face.side-1 .growing-bar:before,
input[name='status']:checked + .content article .chart .bar.bar-2 .face.side-1 .growing-bar:before {
  content: "45";
}

.chart .bar-44 .face.side-0 .growing-bar,
.chart .bar-44 .face.side-1 .growing-bar {
  transform: translateY(56%);
  opacity: .8;
}
.chart .bar-44 .face.side-0 .growing-bar:before,
.chart .bar-44 .face.side-1 .growing-bar:before {
  content: "44";
}

.chart .bar-43 .face.side-0 .growing-bar,
.chart .bar-43 .face.side-1 .growing-bar {
  transform: translateY(57%);
  opacity: .8;
}
.chart .bar-43 .face.side-0 .growing-bar:before,
.chart .bar-43 .face.side-1 .growing-bar:before {
  content: "43";
}

.chart .bar-42 .face.side-0 .growing-bar,
.chart .bar-42 .face.side-1 .growing-bar {
  transform: translateY(58%);
  opacity: .8;
}
.chart .bar-42 .face.side-0 .growing-bar:before,
.chart .bar-42 .face.side-1 .growing-bar:before {
  content: "42";
}

.chart .bar-41 .face.side-0 .growing-bar,
.chart .bar-41 .face.side-1 .growing-bar {
  transform: translateY(59%);
  opacity: .8;
}
.chart .bar-41 .face.side-0 .growing-bar:before,
.chart .bar-41 .face.side-1 .growing-bar:before {
  content: "41";
}

.chart .bar-40 .face.side-0 .growing-bar,
.chart .bar-40 .face.side-1 .growing-bar {
  transform: translateY(60%);
  opacity: .8;
}
.chart .bar-40 .face.side-0 .growing-bar:before,
.chart .bar-40 .face.side-1 .growing-bar:before {
  content: "40";
}

.chart .bar-39 .face.side-0 .growing-bar,
.chart .bar-39 .face.side-1 .growing-bar {
  transform: translateY(61%);
  opacity: .8;
}
.chart .bar-39 .face.side-0 .growing-bar:before,
.chart .bar-39 .face.side-1 .growing-bar:before {
  content: "39";
}

.chart .bar-38 .face.side-0 .growing-bar,
.chart .bar-38 .face.side-1 .growing-bar {
  transform: translateY(62%);
  opacity: .8;
}
.chart .bar-38 .face.side-0 .growing-bar:before,
.chart .bar-38 .face.side-1 .growing-bar:before {
  content: "38";
}

.chart .bar-37 .face.side-0 .growing-bar,
.chart .bar-37 .face.side-1 .growing-bar {
  transform: translateY(63%);
  opacity: .8;
}
.chart .bar-37 .face.side-0 .growing-bar:before,
.chart .bar-37 .face.side-1 .growing-bar:before {
  content: "37";
}

.chart .bar-36 .face.side-0 .growing-bar,
.chart .bar-36 .face.side-1 .growing-bar {
  transform: translateY(64%);
  opacity: .8;
}
.chart .bar-36 .face.side-0 .growing-bar:before,
.chart .bar-36 .face.side-1 .growing-bar:before {
  content: "36";
}

.chart .bar-35 .face.side-0 .growing-bar,
.chart .bar-35 .face.side-1 .growing-bar {
  transform: translateY(65%);
  opacity: .8;
}
.chart .bar-35 .face.side-0 .growing-bar:before,
.chart .bar-35 .face.side-1 .growing-bar:before {
  content: "35";
}

.chart .bar-34 .face.side-0 .growing-bar,
.chart .bar-34 .face.side-1 .growing-bar {
  transform: translateY(66%);
  opacity: .8;
}
.chart .bar-34 .face.side-0 .growing-bar:before,
.chart .bar-34 .face.side-1 .growing-bar:before {
  content: "34";
}

.chart .bar-33 .face.side-0 .growing-bar,
.chart .bar-33 .face.side-1 .growing-bar {
  transform: translateY(67%);
  opacity: .8;
}
.chart .bar-33 .face.side-0 .growing-bar:before,
.chart .bar-33 .face.side-1 .growing-bar:before {
  content: "33";
}

.chart .bar-32 .face.side-0 .growing-bar,
.chart .bar-32 .face.side-1 .growing-bar {
  transform: translateY(68%);
  opacity: .8;
}
.chart .bar-32 .face.side-0 .growing-bar:before,
.chart .bar-32 .face.side-1 .growing-bar:before {
  content: "32";
}

.chart .bar-31 .face.side-0 .growing-bar,
.chart .bar-31 .face.side-1 .growing-bar {
  transform: translateY(69%);
  opacity: .8;
}
.chart .bar-31 .face.side-0 .growing-bar:before,
.chart .bar-31 .face.side-1 .growing-bar:before {
  content: "31";
}

.chart .bar-30 .face.side-0 .growing-bar,
.chart .bar-30 .face.side-1 .growing-bar {
  transform: translateY(70%);
  opacity: .8;
}
.chart .bar-30 .face.side-0 .growing-bar:before,
.chart .bar-30 .face.side-1 .growing-bar:before {
  content: "30";
}

.chart .bar-29 .face.side-0 .growing-bar,
.chart .bar-29 .face.side-1 .growing-bar {
  transform: translateY(71%);
  opacity: .8;
}
.chart .bar-29 .face.side-0 .growing-bar:before,
.chart .bar-29 .face.side-1 .growing-bar:before {
  content: "29";
}

.chart .bar-28 .face.side-0 .growing-bar,
.chart .bar-28 .face.side-1 .growing-bar {
  transform: translateY(72%);
  opacity: .8;
}
.chart .bar-28 .face.side-0 .growing-bar:before,
.chart .bar-28 .face.side-1 .growing-bar:before {
  content: "28";
}

.chart .bar-27 .face.side-0 .growing-bar,
.chart .bar-27 .face.side-1 .growing-bar {
  transform: translateY(73%);
  opacity: .8;
}
.chart .bar-27 .face.side-0 .growing-bar:before,
.chart .bar-27 .face.side-1 .growing-bar:before {
  content: "27";
}

.chart .bar-26 .face.side-0 .growing-bar,
.chart .bar-26 .face.side-1 .growing-bar {
  transform: translateY(74%);
  opacity: .8;
}
.chart .bar-26 .face.side-0 .growing-bar:before,
.chart .bar-26 .face.side-1 .growing-bar:before {
  content: "26";
}

.chart .bar-25 .face.side-0 .growing-bar, input[name='status']:checked + .content article .chart .bar.bar-1 .face.side-0 .growing-bar,
.chart .bar-25 .face.side-1 .growing-bar,
input[name='status']:checked + .content article .chart .bar.bar-1 .face.side-1 .growing-bar {
  transform: translateY(75%);
  opacity: .8;
}
.chart .bar-25 .face.side-0 .growing-bar:before, input[name='status']:checked + .content article .chart .bar.bar-1 .face.side-0 .growing-bar:before,
.chart .bar-25 .face.side-1 .growing-bar:before,
input[name='status']:checked + .content article .chart .bar.bar-1 .face.side-1 .growing-bar:before {
  content: "25";
}

.chart .bar-24 .face.side-0 .growing-bar,
.chart .bar-24 .face.side-1 .growing-bar {
  transform: translateY(76%);
  opacity: .8;
}
.chart .bar-24 .face.side-0 .growing-bar:before,
.chart .bar-24 .face.side-1 .growing-bar:before {
  content: "24";
}

.chart .bar-23 .face.side-0 .growing-bar,
.chart .bar-23 .face.side-1 .growing-bar {
  transform: translateY(77%);
  opacity: .8;
}
.chart .bar-23 .face.side-0 .growing-bar:before,
.chart .bar-23 .face.side-1 .growing-bar:before {
  content: "23";
}

.chart .bar-22 .face.side-0 .growing-bar,
.chart .bar-22 .face.side-1 .growing-bar {
  transform: translateY(78%);
  opacity: .8;
}
.chart .bar-22 .face.side-0 .growing-bar:before,
.chart .bar-22 .face.side-1 .growing-bar:before {
  content: "22";
}

.chart .bar-21 .face.side-0 .growing-bar,
.chart .bar-21 .face.side-1 .growing-bar {
  transform: translateY(79%);
  opacity: .8;
}
.chart .bar-21 .face.side-0 .growing-bar:before,
.chart .bar-21 .face.side-1 .growing-bar:before {
  content: "21";
}

.chart .bar-20 .face.side-0 .growing-bar,
.chart .bar-20 .face.side-1 .growing-bar {
  transform: translateY(80%);
  opacity: .8;
}
.chart .bar-20 .face.side-0 .growing-bar:before,
.chart .bar-20 .face.side-1 .growing-bar:before {
  content: "20";
}

.chart .bar-19 .face.side-0 .growing-bar,
.chart .bar-19 .face.side-1 .growing-bar {
  transform: translateY(81%);
  opacity: .8;
}
.chart .bar-19 .face.side-0 .growing-bar:before,
.chart .bar-19 .face.side-1 .growing-bar:before {
  content: "19";
}

.chart .bar-18 .face.side-0 .growing-bar,
.chart .bar-18 .face.side-1 .growing-bar {
  transform: translateY(82%);
  opacity: .8;
}
.chart .bar-18 .face.side-0 .growing-bar:before,
.chart .bar-18 .face.side-1 .growing-bar:before {
  content: "18";
}

.chart .bar-17 .face.side-0 .growing-bar,
.chart .bar-17 .face.side-1 .growing-bar {
  transform: translateY(83%);
  opacity: .8;
}
.chart .bar-17 .face.side-0 .growing-bar:before,
.chart .bar-17 .face.side-1 .growing-bar:before {
  content: "17";
}

.chart .bar-16 .face.side-0 .growing-bar,
.chart .bar-16 .face.side-1 .growing-bar {
  transform: translateY(84%);
  opacity: .8;
}
.chart .bar-16 .face.side-0 .growing-bar:before,
.chart .bar-16 .face.side-1 .growing-bar:before {
  content: "16";
}

.chart .bar-15 .face.side-0 .growing-bar,
.chart .bar-15 .face.side-1 .growing-bar {
  transform: translateY(85%);
  opacity: .8;
}
.chart .bar-15 .face.side-0 .growing-bar:before,
.chart .bar-15 .face.side-1 .growing-bar:before {
  content: "15";
}

.chart .bar-14 .face.side-0 .growing-bar,
.chart .bar-14 .face.side-1 .growing-bar {
  transform: translateY(86%);
  opacity: .8;
}
.chart .bar-14 .face.side-0 .growing-bar:before,
.chart .bar-14 .face.side-1 .growing-bar:before {
  content: "14";
}

.chart .bar-13 .face.side-0 .growing-bar,
.chart .bar-13 .face.side-1 .growing-bar {
  transform: translateY(87%);
  opacity: .8;
}
.chart .bar-13 .face.side-0 .growing-bar:before,
.chart .bar-13 .face.side-1 .growing-bar:before {
  content: "13";
}

.chart .bar-12 .face.side-0 .growing-bar,
.chart .bar-12 .face.side-1 .growing-bar {
  transform: translateY(88%);
  opacity: .8;
}
.chart .bar-12 .face.side-0 .growing-bar:before,
.chart .bar-12 .face.side-1 .growing-bar:before {
  content: "12";
}

.chart .bar-11 .face.side-0 .growing-bar,
.chart .bar-11 .face.side-1 .growing-bar {
  transform: translateY(89%);
  opacity: .8;
}
.chart .bar-11 .face.side-0 .growing-bar:before,
.chart .bar-11 .face.side-1 .growing-bar:before {
  content: "11";
}

.chart .bar-10 .face.side-0 .growing-bar,
.chart .bar-10 .face.side-1 .growing-bar {
  transform: translateY(90%);
  opacity: .8;
}
.chart .bar-10 .face.side-0 .growing-bar:before,
.chart .bar-10 .face.side-1 .growing-bar:before {
  content: "10";
}

.chart .bar-9 .face.side-0 .growing-bar,
.chart .bar-9 .face.side-1 .growing-bar {
  transform: translateY(91%);
  opacity: .8;
}
.chart .bar-9 .face.side-0 .growing-bar:before,
.chart .bar-9 .face.side-1 .growing-bar:before {
  content: "9";
}

.chart .bar-8 .face.side-0 .growing-bar,
.chart .bar-8 .face.side-1 .growing-bar {
  transform: translateY(92%);
  opacity: .8;
}
.chart .bar-8 .face.side-0 .growing-bar:before,
.chart .bar-8 .face.side-1 .growing-bar:before {
  content: "8";
}

.chart .bar-7 .face.side-0 .growing-bar,
.chart .bar-7 .face.side-1 .growing-bar {
  transform: translateY(93%);
  opacity: .8;
}
.chart .bar-7 .face.side-0 .growing-bar:before,
.chart .bar-7 .face.side-1 .growing-bar:before {
  content: "7";
}

.chart .bar-6 .face.side-0 .growing-bar,
.chart .bar-6 .face.side-1 .growing-bar {
  transform: translateY(94%);
  opacity: .8;
}
.chart .bar-6 .face.side-0 .growing-bar:before,
.chart .bar-6 .face.side-1 .growing-bar:before {
  content: "6";
}

.chart .bar-5 .face.side-0 .growing-bar,
.chart .bar-5 .face.side-1 .growing-bar {
  transform: translateY(95%);
  opacity: .8;
}
.chart .bar-5 .face.side-0 .growing-bar:before,
.chart .bar-5 .face.side-1 .growing-bar:before {
  content: "5";
}

.chart .bar-4 .face.side-0 .growing-bar,
.chart .bar-4 .face.side-1 .growing-bar {
  transform: translateY(96%);
  opacity: .8;
}
.chart .bar-4 .face.side-0 .growing-bar:before,
.chart .bar-4 .face.side-1 .growing-bar:before {
  content: "4";
}

.chart .bar-3 .face.side-0 .growing-bar,
.chart .bar-3 .face.side-1 .growing-bar {
  transform: translateY(97%);
  opacity: .8;
}
.chart .bar-3 .face.side-0 .growing-bar:before,
.chart .bar-3 .face.side-1 .growing-bar:before {
  content: "3";
}

.chart .bar-2 .face.side-0 .growing-bar,
.chart .bar-2 .face.side-1 .growing-bar {
  transform: translateY(98%);
  opacity: .8;
}
.chart .bar-2 .face.side-0 .growing-bar:before,
.chart .bar-2 .face.side-1 .growing-bar:before {
  content: "2";
}

.chart .bar-1 .face.side-0 .growing-bar,
.chart .bar-1 .face.side-1 .growing-bar {
  transform: translateY(99%);
  opacity: .8;
}
.chart .bar-1 .face.side-0 .growing-bar:before,
.chart .bar-1 .face.side-1 .growing-bar:before {
  content: "1";
}

/*
END // CHART'S RULES
*
*
*/
.legend {
  z-index: 100;
  display: flex;
  flex-direction: row;
  justify-content: center;
}

label {
  box-sizing: border-box;
  padding: 1em;
  cursor: pointer;
  transition: all .15s ease-in-out;
  color: #0a4069;
  border: 1px solid rgba(254, 254, 254, 0.6);
  border-radius: 0;
  flex: 0 0 6em;
}
label:first-child {
  margin-right: 0;
  border-radius: .2em 0 0 .2em;
}
label:last-child {
  margin-left: 0;
  border-radius: 0 .2em .2em 0;
}

input[name='status']:checked + .content {
  z-index: 10;
}
input[name='status']:checked + .content article {
  transform: translateX(0);
}
input[name='status']:checked + .content article .chart .bar .growing-bar {
  transition-delay: .3s;
  transition-duration: .6s;
}

input[id='status-1']:checked ~ .legend > label[for='status-1'],
input[id='status-2']:checked ~ .legend > label[for='status-2'],
input[id='status-3']:checked ~ .legend > label[for='status-3'],
input[id='double-size']:checked ~ label[for='double-size'] {
  color: #76c900;
  border: 1px solid #031523;
  background-color: #0a4069;
}

input[id='double-size']:checked + .small-font-size {
  font-size: 2em;
}

input[name='set-value']:checked ~ .content article label[for='set-value'] {
  color: #76c900;
  border: 1px solid #031523;
  background-color: #0a4069;
}
input[name='set-value']:checked ~ .content article .chart .bar.bar-1 .face.side-0 .growing-bar,
input[name='set-value']:checked ~ .content article .chart .bar.bar-1 .face.side-1 .growing-bar, input[name='set-value']:checked ~ .content article .chart .bar.bar-1-1 .face.side-0 .growing-bar,
input[name='set-value']:checked ~ .content article .chart .bar.bar-1-1 .face.side-1 .growing-bar {
  transform: translateY(15%);
}
input[name='set-value']:checked ~ .content article .chart .bar.bar-1 .face.side-0 .growing-bar:before,
input[name='set-value']:checked ~ .content article .chart .bar.bar-1 .face.side-1 .growing-bar:before, input[name='set-value']:checked ~ .content article .chart .bar.bar-1-1 .face.side-0 .growing-bar:before,
input[name='set-value']:checked ~ .content article .chart .bar.bar-1-1 .face.side-1 .growing-bar:before {
  content: '85';
}

</style>

            <div class="face side-1">
              <div class="growing-bar"></div>
            </div>
            <div class="face top"></div>
            <div class="face floor"></div>
          </div>
          <div class="bar bar-1 red">
            <div class="face side-0">
              <div class="growing-bar"></div>
            </div>
            <div class="face side-1">
              <div class="growing-bar"></div>
            </div>
            <div class="face top"></div>
            <div class="face floor"></div>
          </div>
        </div>
      </article>
    </section>
    <nav class="legend">
      <label for="status-1">Tip 1</label>
      <label for="status-2">Tip 2</label>
      <label for="status-3">Tip 3</label>
    </nav>
  </div>
</div> 
