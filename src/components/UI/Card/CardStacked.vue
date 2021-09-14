<template>
  <div class="mt-4 mb-3">
    <h4 class="text-gray-700">Stacked</h4>
    <div class="max-w-sm rounded bg-white overflow-hidden shadow-lg mt-6">
      <img class="w-full" src="https://picsum.photos/id/1016/384/234" alt="Sunset in the mountains" />
      <div class="px-6 py-4">
        <div class="text-gray-900 font-bold text-xl mb-2">The Coldest Sunset</div>
        <p class="text-gray-700 text-base">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis
          eaque, exercitationem praesentium nihil.
        </p>
      </div>
      <div class="px-6 pt-4 pb-2">
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#photography</span
        >
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#travel</span
        >
        <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2"
          >#winter</span
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardStacked',
}
</script>
