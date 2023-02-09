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

<div
	class="bg-[url('/bg-card-front.png')] bg-no-repeat h-[245px] w-[448px] rounded-xl ml-[150px] mt-[75px] shadow-xl text-slate-100"
>
	<div class="text-3xl pt-[130px] w-full text-center tracking-widest ">{cardNumber}</div>
	<div class="flex justify-between mt-5 mx-8  text-sm tracking-wider">
		<div class="uppercase">{name}</div>
		<div>{month}/{year}</div>
	</div>
</div>
