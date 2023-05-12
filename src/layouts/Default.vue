<template>
  <div class="layout bg-gray-200 font-sans leading-normal tracking-normal">
    <div
      class="w-full m-0 p-0 bg-cover bg-bottom"
      style="background-image:url('/cover.jpg'); height: 40vh; max-height:260px;"
    >
      <div
        class="container max-w-4xl mx-auto pt-16 md:pt-15 text-center break-normal"
      >
        <!--Title-->
        <a class="text-blue-500 hover:text-blue-800" href="/">
          <p class="text-white font-extrabold text-3xl md:text-5xl">
            {{ $static.metadata.siteName }}
          </p>
        </a>
        <p class="text-xl md:text-2xl text-gray-500">
          {{ $static.metadata.siteDescription }}
        </p>
      </div>
    </div>
    <slot />
    <footer class="bg-gray-900">
      <div class="container max-w-6xl mx-auto flex items-center px-2 py-8">
        <div class="w-full mx-auto flex flex-wrap items-center">
          <div
            class="flex w-full md:w-1/2 justify-center md:justify-start text-white font-extrabold"
          >
            <a
              class="text-gray-900 no-underline hover:text-gray-900 hover:no-underline"
              href="#"
            >
              👻 <span class="text-base text-gray-200">Ghostwind CSS</span>
            </a>
          </div>
          <div
            class="flex w-full pt-2 content-center justify-between md:w-1/2 md:justify-end"
          >
            <ul
              class="list-reset flex justify-center flex-1 md:flex-none items-center"
            >
              <li>
                <a
                  class="inline-block py-2 px-3 text-white no-underline"
                  href="#"
                  >Active</a
                >
              </li>
              <li>
                <a
                  class="inline-block text-gray-600 no-underline hover:text-gray-200 hover:underline py-2 px-3"
                  href="#"
                  >link</a
                >
              </li>
              <li>
                <a
                  class="inline-block text-gray-600 no-underline hover:text-gray-200 hover:underline py-2 px-3"
                  href="#"
                  >link</a
                >
              </li>
              <li>
                <a
                  class="inline-block text-gray-600 no-underline hover:text-gray-200 hover:underline py-2 px-3"
                  href="#"
                  >link</a
                >
              </li>
            </ul>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<static-query>
query {
  metadata {
    siteName
    siteDescription
  }
}
</static-query>

<style></style>
