<template>
  <header class="flex justify-between border-b border-slate-200 px-10 py-8">
    <div class="flex items-center gap-4">
      <img src="/assets/img/logo.png" alt="Logo" class="w-10" width="40" height="40" />
      <div>
        <h2 class="text-xl font-bold uppercase">shoes vue</h2>
        <p class="text-slate-500">Shop best shoes</p>
      </div>
    </div>

    <ul class="flex items-center gap-8">
      <li class="flex cursor-pointer items-center gap-3 font-bold text-slate-500 hover:text-black">
        <img src="/assets/img/cart.svg" alt="Image" width="18" height="18" /><span>1654 $</span>
      </li>
      <li class="flex cursor-pointer items-center gap-3 text-slate-500 hover:text-black">
        <img src="/assets/img/heart.svg" alt="Image" width="18" height="18" /><span>Favorite</span>
      </li>
      <li class="flex cursor-pointer items-center gap-3 text-slate-500 hover:text-black">
        <img src="/assets/img/profile.svg" alt="Image" width="18" height="18" /><span>User</span>
      </li>
    </ul>
  </header>
</template>
