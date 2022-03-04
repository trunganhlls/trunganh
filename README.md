*,
*::after,
*::before {
	box-sizing: border-box;
}

:root {
	font-size: 18px;
}

@font-face {
	font-family: myFont;
	src: url(Pacifico-Regular.ttf);
  }
  

html, 
body, 
main {
	height: 100%;
	width: 100%;
	position: relative;
	overflow: hidden;
}

body {
	margin: 0;
	--color-text: #d05400;
    --color-bg: #0c0c0c;
    --color-link: #6b5537;
	--color-link-hover: #fff;
	--color-content-title-sub: #6b5537;
    color: var(--color-text);
    background-color: var(--color-bg);
    --cursor-stroke: #6b5537;
    --cursor-fill: none;
    --cursor-stroke-width: 1px;
	font-family: bilo, -apple-system, BlinkMacSystemFont, Segoe UI, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
}

.demo-2 {
	--color-text: #000000;
    --color-bg: #832f05;
    --color-link: #ffffff;
    --color-link-hover: #000;
    --color-content-title-sub: #ec9e34;
    --cursor-stroke: #000000;
    --cursor-fill: none;
    --cursor-stroke-width: 1px;
}

.demo-3 {
	--color-text: #239c34;
    --color-bg: #000000;
    --color-link: #ffffff;
    --color-link-hover: #ccc;
    --color-content-title-sub: #ffffff;
    --cursor-stroke: #239c34;
    --cursor-fill: none;
    --cursor-stroke-width: 3px;
}

a {
	text-decoration: underline;
	color: var(--color-link);
	outline: none;
}

a:hover,
a:focus {
	text-decoration: none;
	color: var(--color-link-hover);
	outline: none;
}

/* Page Loader */
.js .loading::before,
.js .loading::after {
	content: '';
	position: fixed;
	z-index: 1000;
}

.js .loading::before {
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background: var(--color-bg);
}

.js .loading::after {
	top: 50%;
	left: 50%;
	width: 60px;
	height: 60px;
	margin: -30px 0 0 -30px;
	border-radius: 50%;
	opacity: 0.4;
	background: var(--color-link);
	animation: loaderAnim 0.7s linear infinite alternate forwards;

}

@keyframes loaderAnim {
	to {
		opacity: 1;
		transform: scale3d(0.5,0.5,1);
	}
}

.message {
	position: relative;
	z-index: 100;
	text-align: center;
	background: var(--color-text);
	color: var(--color-bg);
	padding: 1rem;
	font-size: 0.85rem;
	position: relative;
}

.no-select {
	-webkit-touch-callout: none;
	-webkit-user-select: none;
	-moz-user-select: none;
	-ms-user-select: none;
	user-select: none;
}

.frame {
	padding: 3rem 5vw;
	text-align: center;
	position: relative;
	z-index: 1000;
}

.frame__title {
	font-size: 1rem;
	margin: 0 0 1rem;
	font-weight: normal;
}

.frame__links {
	display: inline;
}

.frame__links a:not(:last-child),
.frame__demos a:not(:last-child) {
	margin-right: 1rem;
}

.frame__demos {
	margin: 1rem 0;
}

.frame__demo--current,
.frame__demo--current:hover {
	color: var(--color-text);
	text-decoration: none;
}

.content {
	display: flex;
	flex-direction: column;
	width: 100vw;
	height: calc(100vh - 13rem);
	position: relative;
	align-items: center;
	justify-content: center;
	max-height: 300px;
}

.grid {
	pointer-events: none; 
	position: absolute;
	width: 110%;
	height: 110%;
	top: -5%;
	left: -5%;
	display: grid;
	grid-template-columns: repeat(50,2%);
	grid-template-rows: repeat(50,2%);
}

.grid__item {
	position: relative;
	opacity: 0.4,
}

.grid--img .grid__item {
	overflow: hidden;
	display: flex;
	align-items: center;
	justify-content: center;
	will-change: transform;
}

.grid__item-img {
	position: absolute;
	width: 100%;
	height: 100%;
	background-size: cover;
	background-position: 50% 50%;
	z-index: 100;
}

.grid--img .grid__item-img {
	flex: none;
	width: calc(100% + 100px);
	height: calc(100% + 100px);
	will-change: transform;
}

/* Shorthand grid-area: grid-row-start / grid-column-start / grid-row-end / grid-column-end */

.pos-1 {
	grid-area: 10 / 1 / 26 / 7;
}

.pos-2 {
	grid-area: 1 / 18 / 9 / 27;
}

.pos-3 {
	grid-area: 1 / 36 / 14 / 42;
}

.pos-4 {
	grid-area: 13 / 11 / 32 / 18;
}

.pos-5 {
	grid-area: 17 / 32 / 32 / 38;
}

.pos-6 {
	grid-area: 20 / 46 / 28 / 51;
}

.pos-7 {
	grid-area: 43 / 1 / 51 / 10;
}

.pos-8 {
	grid-area: 38 / 14 / 46 / 22;
}

.pos-9 {
	grid-area: 40 / 26 / 51 / 32;
}

.pos-10 {
 	grid-area: 37 / 39 / 48 / 47;
}

.content__title {
	font-family: myFont;
	font-weight: 400;
	font-size: 10vw;
	margin: 10px 0;
	line-height: 1;
	position: relative;
}

.content__title-sub {
	color: var(--color-content-title-sub);
	font-size: 4vw;
	display: block;
	margin-left: 3vw;
	line-height: 0.5;
}

.cursor {
	display: none;
}

@media screen and (min-width: 53em) {
	.message {
		display: none;
	}
	.frame {
		position: fixed;
		text-align: left;
		z-index: 100;
		top: 0;
		left: 0;
		display: grid;
		align-content: space-between;
		width: 100%;
		max-width: none;
		height: 100%;
		padding: 3rem;
		pointer-events: none;
		grid-template-columns: 75% 25%;
		grid-template-rows: auto auto auto;
		grid-template-areas: 'title links'
							'... ...'
							'... demos';
	}
	.frame__title-wrap {
		grid-area: title;
		display: flex;
	}
	.frame__title {
		margin: 0;
	}
	.frame__tagline {
		position: relative;
		margin: 0 0 0 1rem;
		padding: 0 0 0 1rem;
		opacity: 0.5;
	}
	.frame__demos {
		margin: 0;
		grid-area: demos;
		justify-self: end;
	}
	.frame__links {
		grid-area: links;
		padding: 0;
		justify-self: end;
	}
	.frame a {
		pointer-events: auto;
	}
	.content {
		height: 100%;
		justify-content: center;
		max-height: none;
	}
}

.grid__item-img:hover {
	opacity: 1 !important;
	
}

@media (any-pointer: fine) {
	.cursor {
		position: fixed;
		top: 0;
		left: 0;
		display: block;
		pointer-events: none;
	}
	.cursor__inner {
		fill: var(--cursor-fill);
		stroke: var(--cursor-stroke);
		stroke-width: var(--cursor-stroke-width);
	}
}
