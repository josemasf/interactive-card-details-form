<div
	class="bg-[url('/bg-main-desktop.png')] bg-no-repeat h-full lg:h-[95%] lg:w-11/12 lg:my-5 flex w-full"
>
	<div>
		<div
			class="bg-[url('/bg-card-front.png')] bg-no-repeat h-[245px] w-[448px] rounded-xl ml-[150px] mt-[75px] shadow-xl"
		/>
		<div
			class="bg-[url('/bg-card-back.png')] bg-no-repeat h-[245px]  w-[448px] rounded-xl  ml-[225px] mt-10  shadow-xl"
		/>
	</div>
	<div class="flex flex-col gap-3  justify-center ml-20 max-w-sm">
		<div>
			<label for="name" class="pb-1 uppercase font-bold block">Cardholder name</label>
			<input
				id="name"
				class="w-full rounded-lg border-gray-200 p-4 pr-12 text-sm shadow-sm"
				placeholder="e.g. Jane Appleseed"
			/>
		</div>
		<div>
			<label for="card-number" class="pb-1 uppercase font-bold block">Card number</label>
			<input
				id="card-number"
				class="w-full rounded-lg border-gray-200 p-4 pr-12 text-sm shadow-sm"
				placeholder="e.g. 1234 5678 9123 0000"
				maxlength="16"
			/>
		</div>
		<div class="flex gap-5">
			<div>
				<label for="mmyy" class="pb-1 uppercase font-bold block">exp. date (mm/yy)</label>
				<div id="mmyy" class="flex gap-3">
					<input
						id="mm"
						class="w-full rounded-lg border-gray-200 p-4 pr-12 text-sm shadow-sm w-"
						placeholder="MM"
						maxlength="2"
					/><input
						id="yy"
						class="w-full rounded-lg border-gray-200 p-4 pr-12 text-sm shadow-sm"
						placeholder="YY"
						maxlength="2"
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
				/>
			</div>
		</div>
	</div>
</div>

<style lang="postcss">
	:global(html) {
		background-color: theme(colors.gray.100);
	}
</style>
