<script>
	import bookCover from '$assets/book_cover.png';
	import phoneCover from '$assets/phone_cover.png';
	import { Button } from '$components';
</script>

<section class="hero">
	<div class="hero-showcase text-center bold">
		<h1 class="red">MOVE TO</h1>
		<h1 class="red mb-xs">CANADA</h1>
		<h4 class="italic semi-bold">There's no need to make the same mistakes I made.</h4>
		<img class="book-cover" src={bookCover} alt="" />
		<img class="phone-cover" src={phoneCover} alt="" />
	</div>
	<div class="hero-text white text-center">
		<h1>THIS EBOOK WILL</h1>
		<h1>SAVE YOU MONEY,</h1>
		<h1 class="mb-m">TIME & NERVES</h1>
		<p class="light-grey mb-l">
			I moved to Canada four years ago. The process was painful and difficult. I learned most things
			the hard way: finding a job, getting a visa, calculating my cost of living, choosing an
			apartment. That's why I wrote this e-book, to tell you how I did it. No bullshit, no stress.
		</p>
		<Button>Purchase E-book for $99999</Button>
	</div>
</section>

<style>
	.hero {
		display: flex;
		height: 100vh;
		overflow-y: hidden;
	}

	.hero-showcase {
		position: relative;
		width: 50%;
		padding: 100px 16px 0 16px;
		background: linear-gradient(
			135deg,
			#f9c2c2,
			#f9c2c2 25%,
			#f7a1a1 50%,
			#f4bebe 75%,
			#c95656 100%
		);
	}

	.hero-text {
		padding: 100px 5%;
		width: 50%;
		background-color: black;
	}

	.book-cover {
		position: absolute;
		right: 2%;
		bottom: 0;
		width: 65%;
		transform: translateY(30%);
	}

	.phone-cover {
		position: absolute;
		width: 35%;
		bottom: 0;
		right: 52%;
		transform: translateY(25%);
	}
</style>
