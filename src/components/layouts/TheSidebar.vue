<template>
  <aside class="hidden w-64 bg-gray-800 sm:block">
    <div class="py-3 text-2xl uppercase text-center tracking-widest bg-gray-900 border-b-2 border-gray-800 mb-8">
      <a href="#" class="text-white">Tailmin</a>
    </div>

    <nav class="text-sm text-gray-300">
      <ul class="flex flex-col">
        <li class="px-4 py-2 text-xs uppercase tracking-wider text-gray-500 font-bold">Section</li>

        <li class="px-4 cursor-pointer bg-gray-500 text-gray-800">
          <a href="#" class="py-3 flex items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 mr-2"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6"
              />
            </svg>
            Dashboard
          </a>
        </li>

        <li>
          <Disclosure v-slot="{ open }">
            <DisclosureButton
              class="px-4 py-3 flex items-center w-full hover:bg-gray-700"
              :class="open ? 'bg-gray-700' : ''"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-5 w-5 mr-2"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M17 20h5v-2a3 3 0 00-5.356-1.857M17 20H7m10 0v-2c0-.656-.126-1.283-.356-1.857M7 20H2v-2a3 3 0 015.356-1.857M7 20v-2c0-.656.126-1.283.356-1.857m0 0a5.002 5.002 0 019.288 0M15 7a3 3 0 11-6 0 3 3 0 016 0zm6 3a2 2 0 11-4 0 2 2 0 014 0zM7 10a2 2 0 11-4 0 2 2 0 014 0z"
                />
              </svg>
              User Management
              <span class="ml-auto">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  class="h-5 w-5"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                  :class="open ? 'transform rotate-90' : ''"
                >
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                </svg>
              </span>
            </DisclosureButton>
            <DisclosurePanel>
              <ul>
                <li>
                  <Disclosure v-slot="{ open }">
                    <DisclosureButton
                      class="pl-8 pr-4 py-3 flex items-center w-full hover:bg-gray-700"
                      :class="open ? 'bg-gray-700' : ''"
                    >
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="currentColor" viewBox="0 0 16 16">
                        <path d="M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3z" />
                      </svg>
                      Users
                      <span class="ml-auto">
                        <svg
                          xmlns="http://www.w3.org/2000/svg"
                          class="h-5 w-5"
                          fill="none"
                          viewBox="0 0 24 24"
                          stroke="currentColor"
                          :class="open ? 'transform rotate-90' : ''"
                        >
                          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                        </svg>
                      </span>
                    </DisclosureButton>
                    <DisclosurePanel>
                      <ul>
                        <li class="pl-12 hover:bg-gray-700">
                          <a href="#" class="py-3 flex items-center">
                            <svg
                              xmlns="http://www.w3.org/2000/svg"
                              class="h-5 w-5"
                              fill="currentColor"
                              viewBox="0 0 16 16"
                            >
                              <path d="M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3z" />
                            </svg>
                            User List
                          </a>
                        </li>
                        <li class="pl-12 hover:bg-gray-700">
                          <a href="#" class="py-3 flex items-center">
                            <svg
                              xmlns="http://www.w3.org/2000/svg"
                              class="h-5 w-5"
                              fill="currentColor"
                              viewBox="0 0 16 16"
                            >
                              <path d="M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3z" />
                            </svg>
                            User Detail
                          </a>
                        </li>
                      </ul>
                    </DisclosurePanel>
                  </Disclosure>
                </li>
                <li class="px-8 hover:bg-gray-700">
                  <a href="#" class="py-3 flex items-center">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="currentColor" viewBox="0 0 16 16">
                      <path d="M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3z" />
                    </svg>
                    Roles
                  </a>
                </li>
                <li class="px-8 hover:bg-gray-700">
                  <a href="#" class="py-3 flex items-center">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="currentColor" viewBox="0 0 16 16">
                      <path d="M8 9.5a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3z" />
                    </svg>
                    Permissions
                  </a>
                </li>
              </ul>
            </DisclosurePanel>
          </Disclosure>
        </li>

        <li class="px-4 hover:bg-gray-700">
          <a href="#" class="py-3 flex items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 mr-2"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M11 3.055A9.001 9.001 0 1020.945 13H11V3.055z"
              />
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M20.488 9H15V3.512A9.025 9.025 0 0120.488 9z"
              />
            </svg>
            Reports
          </a>
        </li>

        <li class="px-4 py-2 mt-2 text-xs uppercase tracking-wider text-gray-500 font-bold">Apps</li>

        <li class="px-4 cursor-pointer hover:bg-gray-700">
          <a href="#" class="py-2 flex items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 mr-2"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
              />
            </svg>
            Messages
            <span class="ml-auto text-xs bg-gray-500 px-2 py-1 rounded-sm">16</span>
          </a>
        </li>

        <li class="px-4 cursor-pointer hover:bg-gray-700">
          <a href="#" class="py-2 flex items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 mr-2"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M8 7V3m8 4V3m-9 8h10M5 21h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v12a2 2 0 002 2z"
              />
            </svg>
            Calendar
          </a>
        </li>

        <li class="px-4 py-2 mt-2 text-xs uppercase tracking-wider text-gray-500 font-bold">Pages</li>

        <li class="px-4 cursor-pointer hover:bg-gray-700">
          <router-link :to="{ name: 'login' }" class="py-2 flex items-center">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              class="h-5 w-5 mr-2"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M15 7a2 2 0 012 2m4 0a6 6 0 01-7.743 5.743L11 17H9v2H7v2H4a1 1 0 01-1-1v-2.586a1 1 0 01.293-.707l5.964-5.964A6 6 0 1121 9z"
              />
            </svg>
            Login
          </router-link>
        </li>
      </ul>
    </nav>
  </aside>
</template>

<script>
import { Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue'

export default {
  components: {
    Disclosure,
    DisclosureButton,
    DisclosurePanel,
  },
}
</script>
