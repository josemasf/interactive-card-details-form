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

<div class="w-fit rounded-xl  text-slate-100 md:mt-10 md:ml-28">
	<div class="relative z-10 top-36 md:top-48 mx-8">
		<div class="text-lg md:text-3xl w-full text-center tracking-widest">{cardNumber}</div>
		<div class="flex justify-between text-sm tracking-wider mt-5">
			<div class="uppercase">{name}</div>
			<div>{month}/{year}</div>
		</div>
	</div>
	<img src="/bg-card-front.png" alt="card front side" class="z-0 shadow-xl" />
</div>
