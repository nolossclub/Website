<template>
  <div class="container mx-auto max-w-7xl px-5">
    <div class="py-10">
      <div class="flex md:flex-row flex-col items-center">
        <div class="md:w-1/2 p-5">
          <p class="text-3xl font-bold uppercase text-gray-600">
            NOLOSSCLUB is a crypto-powered savings protocol based on Defi
            lending. Save money and have a chance to win every week.
          </p>

          <div
            class="py-3 items-center mx-auto space-y-6 text-center uppercase text-base font-bold"
          >
            <div class="relative flex flex-col md:flex-row md:space-x-4">
              <a
                href="https://bscscan.com/token/0xa4c46822896B1f7B4f68C073EdB5fcCd09ba2a0b#balances"
                class="flex items-center w-full px-6 py-3 mb-3 text-white bg-gray-400 rounded-md md:mb-0 md:w-auto"
              >
                bscscan
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-4 h-4 ml-1"
                  viewBox="0 0 24 24"
                >
                  <path d="M5 12h14M12 5l7 7-7 7"></path>
                </svg>
              </a>
              <a
                href="https://matcha.xyz/markets/56/0xa4c46822896b1f7b4f68c073edb5fccd09ba2a0b"
                class="flex items-center w-full px-6 py-3 mb-3 text-white bg-gray-400 rounded-md md:mb-0 md:w-auto"
              >
                BUY TOKEN
                <svg
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  class="w-4 h-4 ml-1"
                  viewBox="0 0 24 24"
                >
                  <path d="M5 12h14M12 5l7 7-7 7"></path>
                </svg>
              </a>
            </div>
          </div>
        </div>

        <div class="md:w-1/2 p-5">
          <lottie-player
            class="object-cover object-center"
            autoplay=""
            loop=""
            mode="normal"
            src="/assets/1.json"
            background="transparent"
          ></lottie-player>
        </div>
      </div>
    </div>
  </div>
</template>
