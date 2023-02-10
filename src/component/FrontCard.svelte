<script lang="ts">
	export let number: string;
	export let name: string;
	export let month: number;
	export let year: number;

	function creditCardNumber(value: string, pattern: string) {
		let i = 0;
		const v = value.toString().replaceAll(' ', '');

		return pattern.replace(/#/g, (_) => v[i++]).replaceAll('undefined', '');
	}

	$: cardNumber = creditCardNumber(number, '#### #### #### ####');
</script>

<div class="w-fit rounded-xl  text-slate-100 ">
	<div class="relative z-10 top-60 md:top-60 mx-8">
		<div class="text-lg md:text-xl lg:text-3xl w-full text-center tracking-widest">
			{cardNumber}
		</div>
		<div class="flex justify-between text-sm tracking-wider mt-5">
			<div class="uppercase">{name}</div>
			<div>{month}/{year}</div>
		</div>
	</div>
	<div class="relative top-20 left-8 ">
		<svg width="84" height="47" fill="none" xmlns="http://www.w3.org/2000/svg"
			><ellipse cx="23.478" cy="23.5" rx="23.478" ry="23.5" fill="#fff" /><path
				d="M83.5 23.5c0 5.565-4.507 10.075-10.065 10.075-5.559 0-10.065-4.51-10.065-10.075 0-5.565 4.506-10.075 10.065-10.075 5.558 0 10.065 4.51 10.065 10.075Z"
				stroke="#fff"
			/></svg
		>
	</div>
	<img src="/bg-card-front.png" alt="card front side" class="z-0 shadow-xl" />
</div>
