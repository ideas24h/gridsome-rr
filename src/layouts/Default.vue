<template>
  <div class="font-sans max-w-5xl mx-auto sm:mx-2 sm:p-2 lg:mx-auto container">
    <header >
      <nav class="flex items-center justify-between flex-wrap bg-teal-500 p-6">
        <div class="flex items-center flex-shrink-0  text-white mr-6">
          <!-- <svg class="fill-current h-8 w-8 mr-2" width="54" height="54" viewBox="0 0 54 54" xmlns="http://www.w3.org/2000/svg"><path d="M13.5 22.1c1.8-7.2 6.3-10.8 13.5-10.8 10.8 0 12.15 8.1 17.55 9.45 3.6.9 6.75-.45 9.45-4.05-1.8 7.2-6.3 10.8-13.5 10.8-10.8 0-12.15-8.1-17.55-9.45-3.6-.9-6.75.45-9.45 4.05zM0 38.3c1.8-7.2 6.3-10.8 13.5-10.8 10.8 0 12.15 8.1 17.55 9.45 3.6.9 6.75-.45 9.45-4.05-1.8 7.2-6.3 10.8-13.5 10.8-10.8 0-12.15-8.1-17.55-9.45-3.6-.9-6.75.45-9.45 4.05z"/></svg> -->
          <span class="font-bold text-4xl tracking-tight">
                    <g-link  to="/">{{ $static.metaData.siteName }}</g-link>
          </span>
        </div>
        <div class="block lg:hidden">
          <button class="flex items-center px-3 py-2 border rounded text-teal-200 border-teal-400 hover:text-white hover:border-white">
            <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/></svg>
          </button>
        </div>
        <div class="w-full block flex-grow lg:flex lg:items-center lg:w-auto">
          <div class="text-sm lg:flex-grow">
          </div>
          <!-- <div>
            <a href="#" class="inline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-teal-500 hover:bg-white mt-4 lg:mt-0">Download</a>
          </div> -->
        </div>
      </nav>  
    </header>
    <slot/>
    <div class="bg-white border-t">
    <div class="container mx-auto px-4">
      <div class="md:flex justify-between items-center text-sm">
        <div class="text-center md:text-left py-3 md:py-4 border-b md:border-b-0">
              <g-link class="block mt-4 lg:inline-block lg:mt-0 text-grey-200 hover:text-gray-800 mr-4" to="/">Home</g-link>
              <g-link class="block mt-4 lg:inline-block lg:mt-0 text-grey-200 hover:text-grsy-800 mr-4" to="/about">Acerca de</g-link>
              <g-link class="block mt-4 lg:inline-block lg:mt-0 text-grey-200 hover:text-gray-800 mr-4" to="/afiliados">Afiliados</g-link>
        </div>
        <div class="md:flex md:flex-row-reverse items-center py-4">
          <div class="text-center mb-4 md:mb-0 md:flex">
          </div>
          <div class="text-grey text-center text-gray-400 md:mr-4">&copy; 2019 ideas24h</div>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>
