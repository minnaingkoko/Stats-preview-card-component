<script>
	import MediaQuery from "./MediaQuery.svelte";
</script>

<main class="home">
	<div class="container">
		<div class="left">
			<h1 class="heading">Get <div class="highlight">insights</div> that help your business grow.</h1>
			<p class="text">Discover the benefits of data analytics and make better decisions regarding revenue, customer experience, and overall efficiency.</p>
			<div class="rate">
				<div class="stat">
					<div class="stat_number">10k+</div>
					<div class="stat_text">COMPANIES</div>
				</div>
				<div class="stat">
					<div class="stat_number">314</div>
					<div class="stat_text">TEMPLATES</div>
				</div>
				<div class="stat">
					<div class="stat_number">12M+</div>
					<div class="stat_text">QUERIES</div>
				</div>
			</div>
		</div>
		<div class="right">
			<div class="overlay"></div>
			<MediaQuery query="(max-width: 717px)" let:matches>
				{#if matches}
					<img class="business" src="/images/image-header-mobile.jpg" alt="">
				{:else}
					<img class="business" src="/images/image-header-desktop.jpg" alt="">
				{/if}
			</MediaQuery>
		</div>
	</div>
</main>

<style>
	.home {
		@apply w-screen h-screen flex justify-center items-center bg-[#090b1a];
	}
	.container {
		@apply w-[1115px] h-[450px] rounded-[10px] flex flex-row;
	}
	.left, .right {
		@apply w-[50%] h-[100%];
	}
	.left {
		@apply bg-[#1b1938] rounded-tl-[10px] rounded-bl-[10px] flex flex-col p-[60px] pr-[120px];
	}
	.heading {
		@apply text-[36px] text-[#ffffff] font-bold font-['Inter'];
	}
	.highlight {
		@apply inline-block text-[#aa5cdb] text-[32px];
	}
	.text {
		@apply mt-[32px] text-white/75;
	}
	.rate {
		@apply mt-[72px] flex flex-row gap-[60px];
	}
	.stat {
		@apply flex flex-col font-['Inter'];
	}
	.stat_number {
		@apply text-[#ffffff] text-[20px] font-bold;
	}
	.stat_text {
		@apply text-white/[.6] text-[12px];
	}
	.right {
		@apply relative;
	}
	.overlay {
		@apply bg-[#aa5cdb] opacity-[0.4] rounded-tr-[10px] rounded-br-[10px] w-[100%] h-[100%] absolute;
	}
	.business {
		@apply w-[100%] h-[100%] rounded-tr-[10px] rounded-br-[10px] object-cover;
	}
	@media only screen and (max-width: 1150px) {
		.container {
			width: calc(100% - 32px);
		}
		.heading, .highlight {
			font-size: 32px;
		}
		.left {
			padding-left: 50px;
			padding-right: 100px;
		}
	}
	@media only screen and (max-width: 1024px) {
		.heading, .highlight {
			font-size: 28px;
		}
		.left {
			padding-left: 40px;
			padding-right: 80px;
		}
	}
	@media only screen and (max-width: 960px) {
		.left {
			padding-left: 30px;
			padding-right: 60px;
		}
	}
	@media only screen and (max-width: 832px) {
		.heading, .highlight {
			font-size: 24px;
		}
		.rate {
			justify-content: space-between;
			gap: 0;
		}
	}
	@media only screen and (max-width: 717px) {
		.container {
			flex-direction: column-reverse;
			width: 450px;
			height: auto;
		}
		.left, .right {
			width: 450px;
		}
		.heading, .highlight {
			font-size: 36px;
			text-align: center;
		}
		.left {
			border-radius: 0 0 10px 10px;
			padding: 5% 10%;
		}
		.right, .business, .overlay {
			border-radius: 10px 10px 0 0;
		}
	}
	@media only screen and (max-width: 500px) {
		.container {
			width: calc(100% - 32px);
		}
		.left, .right {
			width: 100%;
		}
	}
	@media only screen and (max-width: 365px) {
		.heading, .highlight {
			font-size: 28px;
		}
	}
</style>
