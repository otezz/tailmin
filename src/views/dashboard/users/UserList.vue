<template>
  <div class="flex justify-between px-4 mt-4 sm:px-8">
    <h2 class="text-2xl text-gray-600">User List</h2>

    <div class="flex items-center space-x-1 text-xs">
      <router-link to="/" class="font-bold text-indigo-700">Home</router-link>
      <svg xmlns="http://www.w3.org/2000/svg" class="h-2 w-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
      </svg>
      <span class="text-gray-600">Users</span>
    </div>
  </div>

  <div class="p-4 mt-8 sm:px-8 sm:py-4">
    <div class="p-4 bg-white rounded">
      <div class="flex justify-between">
        <div>
          <div class="relative text-gray-400">
            <span class="absolute inset-y-0 left-0 flex items-center pl-2">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-6 w-6"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
                />
              </svg>
            </span>
            <input
              id="search"
              name="search"
              type="search"
              class="
                w-full
                py-2
                text-sm text-gray-900
                rounded-md
                pl-10
                border border-gray-300
                focus:outline-none focus:ring-gray-500 focus:ring-gray-500 focus:z-10
              "
              placeholder="Search user"
            />
          </div>
        </div>
        <div>
          <div>
            <button class="flex items-center bg-green-500 p-2 text-white rounded text-sm hover:bg-green-600">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="h-6 w-6 mr-1"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
              </svg>

              Create New
            </button>
          </div>
        </div>
      </div>
      <table class="w-full mt-2 text-gray-500">
        <thead class="border-b">
          <tr>
            <th class="p-2 text-left text-gray-600">
              <input
                v-model="selectAll"
                type="checkbox"
                class="h-5 w-5 text-blue-500 border-gray-300 rounded cursor-pointer focus:ring-0"
              />
            </th>
            <th class="text-left text-gray-600">USER</th>
            <th class="text-left text-gray-600">ROLE</th>
            <th class="text-left text-gray-600">STATUS</th>
            <th class="text-left text-gray-600">LAST ACTIVITY</th>
            <th class="text-left text-gray-600">JOIN DATE</th>
            <th class="text-right text-gray-600">ACTIONS</th>
          </tr>
        </thead>
        <tbody class="divide-y divide-gray-200">
          <tr v-for="user in userList" :key="user.id">
            <td class="p-2">
              <input
                type="checkbox"
                class="h-5 w-5 text-blue-500 border-gray-300 rounded cursor-pointer focus:ring-0"
                :checked="selectAll"
              />
            </td>
            <td class="flex items-center py-4">
              <img class="inline-block h-12 w-12 rounded-full ring-2 ring-white" :src="user.avatar" alt="" />
              <div class="px-4">
                <div>
                  <a href="#" class="text-gray-600 font-bolder">{{ user.name }}</a>
                </div>
                <div class="font-bold text-sm">
                  {{ user.email }}
                </div>
              </div>
            </td>
            <td>{{ user.role }}</td>
            <td>
              <span v-if="user.isActive" class="px-2 py-1 rounded text-xs text-white bg-green-500">Active</span>
              <span v-else class="px-2 py-1 rounded text-xs text-white bg-red-500">Suspended</span>
            </td>
            <td>{{ user.lastActivity }}</td>
            <td>{{ user.joinDate }}</td>
            <td class="text-right">
              <Menu as="div" class="relative inline-block text-left">
                <div>
                  <MenuButton
                    class="
                      inline-flex
                      justify-center
                      w-full
                      px-4
                      py-2
                      text-sm
                      font-medium
                      text-white
                      rounded-md
                      bg-gray-500
                      hover:bg-gray-600
                      focus:outline-none
                      focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75
                    "
                  >
                    Actions
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      class="w-5 h-5 ml-2 -mr-1 text-violet-200 hover:text-violet-100"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke="currentColor"
                    >
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
                    </svg>
                  </MenuButton>
                </div>

                <transition
                  enter-active-class="transition duration-100 ease-out"
                  enter-from-class="transform scale-95 opacity-0"
                  enter-to-class="transform scale-100 opacity-100"
                  leave-active-class="transition duration-75 ease-in"
                  leave-from-class="transform scale-100 opacity-100"
                  leave-to-class="transform scale-95 opacity-0"
                >
                  <MenuItems
                    class="
                      absolute
                      right-0
                      w-32
                      mt-1
                      origin-top-right
                      bg-white
                      divide-y divide-gray-100
                      rounded-md
                      shadow-lg
                      ring-1 ring-black ring-opacity-5
                      z-50
                      focus:outline-none
                    "
                  >
                    <div class="px-1 py-1">
                      <MenuItem v-slot="{ active }">
                        <button
                          :class="[
                            active ? 'bg-gray-400 text-white' : 'text-gray-900',
                            'group flex rounded-md items-center w-full px-2 py-2 text-sm',
                          ]"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="w-5 h-5 mr-2 text-violet-400"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                          >
                            <path
                              stroke-linecap="round"
                              stroke-linejoin="round"
                              stroke-width="2"
                              d="M15.232 5.232l3.536 3.536m-2.036-5.036a2.5 2.5 0 113.536 3.536L6.5 21.036H3v-3.572L16.732 3.732z"
                            />
                          </svg>
                          Edit
                        </button>
                      </MenuItem>
                      <MenuItem v-slot="{ active }">
                        <button
                          :class="[
                            active ? 'bg-red-400 text-white' : 'text-gray-900',
                            'group flex rounded-md items-center w-full px-2 py-2 text-sm',
                          ]"
                        >
                          <svg
                            xmlns="http://www.w3.org/2000/svg"
                            class="w-5 h-5 mr-2 text-violet-400"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                          >
                            <path
                              stroke-linecap="round"
                              stroke-linejoin="round"
                              stroke-width="2"
                              d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16"
                            />
                          </svg>
                          Delete
                        </button>
                      </MenuItem>
                    </div>
                  </MenuItems>
                </transition>
              </Menu>
            </td>
          </tr>
        </tbody>
        <tfoot>
          <tr>
            <td colspan="7" class="py-2">
              <div class="hidden sm:flex-1 sm:flex sm:items-center sm:justify-between">
                <div>
                  <p class="text-sm text-gray-500">
                    Showing
                    <span class="font-medium">1</span>
                    to
                    <span class="font-medium">5</span>
                    of
                    <span class="font-medium">42</span>
                    results
                  </p>
                </div>
                <div>
                  <nav class="relative z-0 inline-flex rounded-md shadow-sm -space-x-px" aria-label="Pagination">
                    <a
                      href="#"
                      class="
                        relative
                        inline-flex
                        items-center
                        px-2
                        rounded-l-md
                        border border-gray-300
                        text-sm
                        font-medium
                        text-gray-500
                        hover:bg-gray-50
                      "
                    >
                      <span class="sr-only">Previous</span>
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-6 w-6"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                      >
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
                      </svg>
                    </a>
                    <!-- Current: "z-10 bg-indigo-50 border-indigo-500 text-indigo-600", Default: "bg-white border-gray-300 text-gray-500 hover:bg-gray-50" -->
                    <a
                      href="#"
                      aria-current="page"
                      class="
                        z-10
                        bg-indigo-50
                        border-indigo-500
                        text-indigo-600
                        relative
                        inline-flex
                        items-center
                        px-4
                        py-1
                        border
                        text-sm
                        font-medium
                      "
                    >
                      1
                    </a>
                    <a
                      href="#"
                      class="
                        border-gray-300
                        text-gray-500
                        hover:bg-gray-50
                        relative
                        inline-flex
                        items-center
                        px-4
                        py-1
                        border
                        text-sm
                        font-medium
                      "
                    >
                      2
                    </a>
                    <a
                      href="#"
                      class="
                        border-gray-300
                        text-gray-500
                        hover:bg-gray-50
                        hidden
                        md:inline-flex
                        relative
                        items-center
                        px-4
                        py-1
                        border
                        text-sm
                        font-medium
                      "
                    >
                      3
                    </a>
                    <span
                      class="
                        relative
                        inline-flex
                        items-center
                        px-4
                        py-1
                        border border-gray-300
                        text-sm
                        font-medium
                        text-gray-700
                      "
                    >
                      ...
                    </span>
                    <a
                      href="#"
                      class="
                        border-gray-300
                        text-gray-500
                        hover:bg-gray-50
                        hidden
                        md:inline-flex
                        relative
                        items-center
                        px-4
                        py-1
                        border
                        text-sm
                        font-medium
                      "
                    >
                      8
                    </a>
                    <a
                      href="#"
                      class="
                        border-gray-300
                        text-gray-500
                        hover:bg-gray-50
                        relative
                        inline-flex
                        items-center
                        px-4
                        py-1
                        border
                        text-sm
                        font-medium
                      "
                    >
                      9
                    </a>
                    <a
                      href="#"
                      class="
                        border-gray-300
                        text-gray-500
                        hover:bg-gray-50
                        relative
                        inline-flex
                        items-center
                        px-4
                        py-1
                        border
                        text-sm
                        font-medium
                      "
                    >
                      10
                    </a>
                    <a
                      href="#"
                      class="
                        relative
                        inline-flex
                        items-center
                        px-2
                        py-1
                        rounded-r-md
                        border border-gray-300
                        text-sm
                        font-medium
                        text-gray-500
                        hover:bg-gray-50
                      "
                    >
                      <span class="sr-only">Next</span>
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        class="h-6 w-6"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                      >
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                      </svg>
                    </a>
                  </nav>
                </div>
              </div>
            </td>
          </tr>
        </tfoot>
      </table>
    </div>
  </div>
</template>

<script>
import userList from '@/data/users/userList.json'
import { Menu, MenuButton, MenuItems, MenuItem } from '@headlessui/vue'
import { ref } from 'vue'

export default {
  components: {
    Menu,
    MenuButton,
    MenuItems,
    MenuItem,
  },

  setup() {
    const selectAll = ref(false)

    return {
      userList,
      selectAll,
    }
  },
}
</script>
