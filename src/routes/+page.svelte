<script>
	import FrontCard from '../component/FrontCard.svelte';
	import BackCard from '../component/BackCard.svelte';

	const currentYear = new Date().getFullYear().toString().substring(2, 4);

	const creditCard = {
		number: '0000000000000000',
		name: 'Joe Smith',
		year: Number(currentYear),
		month: 1,
		cvv2: 123
	};

	/**
	 * @param {{ code: string; preventDefault: () => void; }} event
	 */
	function handleKeydown(event) {
		console.log(event.code);
		if (event.code === 'Space') event.preventDefault();
	}
</script>

<div
	class="bg-[url('/bg-main-mobile.png')] md:bg-[url('/bg-main-desktop.png')] bg-no-repeat h-full lg:h-[95%] lg:w-11/12 lg:my-5 md:flex  w-full shadow-xl bg-slate-100"
>
	<div>
		<FrontCard {...creditCard} />
		<BackCard {...creditCard} />
	</div>
	<div class="flex flex-col gap-3  justify-center ml-20 max-w-sm">
		<div>
			<label for="name" class="pb-1 uppercase font-bold block">Cardholder name</label>
			<input
				id="name"
				class="w-full rounded-lg border-gray-200 p-4 pr-12 text-sm shadow-sm"
				placeholder="e.g. Jane Appleseed"
				bind:value={creditCard.name}
			/>
		</div>
		<div>
			<label for="card-number" class="pb-1 uppercase font-bold block">Card number</label>
			<input
				id="card-number"
				class="w-full rounded-lg border-gray-200 p-4 pr-12 text-sm shadow-sm"
				placeholder="e.g. 1234 5678 9123 0000"
				on:keydown={handleKeydown}
				maxlength="16"
				bind:value={creditCard.number}
			/>
		</div>
		<div class="flex gap-5">
			<div>
				<label for="mmyy" class="pb-1 uppercase font-bold block">exp. date (mm/yy)</label>
				<div id="mmyy" class="flex gap-3">
					<input
						type="number"
						id="mm"
						class=" block
                        w-full
                        px-3
                        py-3
                        rounded
                        transition
                        ease-in-out
                        m-0
                        focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none"
						placeholder="MM"
						maxlength="2"
						min="1"
						max="12"
						bind:value={creditCard.month}
					/><input
						type="number"
						id="yy"
						class="form-control
                        block
                        w-full
                        px-3
                        py-3
                        rounded
                        transition
                        ease-in-out
                        my-0
                        focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none"
						placeholder="YY"
						maxlength="2"
						min={currentYear}
						bind:value={creditCard.year}
					/>
				</div>
			</div>
			<div class="min-w-[180px]">
				<label for="cvv" class="pb-1 uppercase font-bold block">CVV2</label>
				<input
					id="cvv"
					class="w-full rounded-lg border-gray-200 p-4 pr-12 text-sm shadow-sm"
					placeholder="123"
					maxlength="3"
					bind:value={creditCard.cvv2}
				/>
			</div>
		</div>
		<div>
			<button
				class="block w-full  mx-auto bg-[#21092F] hover:bg-indigo-700 focus:bg-indigo-700 text-white rounded-lg px-3 py-3 font-semibold"
				><i class="lg:i lg:i-lock-outline mr-1" /> Confirm</button
			>
		</div>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.gray.100);
	}
</style>
