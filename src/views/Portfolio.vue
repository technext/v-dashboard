<template>
  <div>
    <h3 class="text-3xl font-medium text-gray-700">{{ Class.name }}</h3>
    <div class="flex flex-col mt-8">
      <div class="py-2 -my-2 overflow-x-auto sm:-mx-6 sm:px-6 lg:-mx-8 lg:px-8">
        <div
          class="inline-block min-w-full overflow-hidden align-middle border-b border-gray-200 shadow sm:rounded-lg"
        >
          <table class="min-w-full">
            <thead>
              <tr>
                <th
                  class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase border-b border-gray-200 bg-gray-50"
                >
                  Name
                </th>
                <th
                  class="px-6 py-3 text-xs font-medium leading-4 tracking-wider text-left text-gray-500 uppercase border-b border-gray-200 bg-gray-50"
                >
                  Url
                </th>
                <th class="px-6 py-3 border-b border-gray-200 bg-gray-50"></th>
              </tr>
            </thead>

            <tbody class="bg-white">
              <tr v-for="(u, index) in users" :key="index"
              >
                <td
                  class="px-6 py-4 border-b border-gray-200 whitespace-nowrap"
                >
                  <div class="flex items-center">
                    <div class="flex-shrink-0 w-10 h-10">
                      <img
                        class="w-10 h-10 rounded-full"
                        src="https://images.unsplash.com/photo-1472099645785-5658abf4ff4e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=2&w=256&h=256&q=80"
                        alt=""
                      />
                    </div>

                    <div class="ml-4">
                      <div class="text-sm font-medium leading-5 text-gray-900">
                        {{ u.name }}
                      </div>
                    </div>
                  </div>
                </td>
                
                <td
                  class="px-6 py-4 border-b border-gray-200 whitespace-nowrap"
                     
                  
                >
                  <a class="text-sm leading-5 text-gray-900"
                  target="_blank"
                  :href="u.url"
                  >
                    {{ u.url }}
                  </a>
                </td>
                
                
                
                <td
                  class="px-6 py-4 text-sm font-medium leading-5 text-right border-b border-gray-200 whitespace-nowrap"
                >
                  <a href="#" class="text-indigo-600 hover:text-indigo-900"
                    >Edit</a
                  >
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

interface User {
  name: string;
  url: string;
}

interface Class {
  name: string;
}

export default defineComponent({
  setup() {
    const Class: Class = {
      name: "1반",
    };

    const testUser: User = {
      name: "윤서준",
      url: "https://marred-algebra-69b.notion.site/d5f8561a0536455d804d025786b8775c",
    };

    const users = ref<User[]>([...Array(20).keys()].map(() => testUser));

    return {
      users,
      Class,
    };
  },
});
</script>
