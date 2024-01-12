<script setup>
import { Icon } from "@iconify/vue";
import { ref } from "vue";
import { onMounted, onUnmounted } from "vue";

const showSidebar = ref(false);

const sideBar = () => {
  showSidebar.value = !showSidebar.value;
};

onMounted(() => {
  const handleClickOutside = (event) => {
    const menuButton = document.querySelector(".menu-button");
    const menuContent = document.querySelector(".menu-content");

    if (
      menuButton &&
      menuContent &&
      !menuContent.contains(event.target) &&
      !menuButton.contains(event.target)
    ) {
      showSidebar.value = false;
    }
  };

  document.addEventListener("click", handleClickOutside);

  // Cleanup the event listener when the component is unmounted
  onUnmounted(() => {
    document.removeEventListener("click", handleClickOutside);
  });
});

const backGround = ref(
  "https://i.pinimg.com/736x/3d/8c/2f/3d8c2f2c82c1c9ef1e27be645cd1aa17.jpg"
);
</script>

<template>
  <div class="flex">
    <div
      class="bg-[#324d66] h-screen w-1/12 flex flex-col pt-5 items-center menu-button"
    >
      <button @click="sideBar">
        <Icon icon="ic:outline-menu" class="mx-3 text-3xl text-[#7A8C9E]" />
      </button>
      <button class="py-2 px-5 flex flex-col items-center">
        <Icon
          icon="ion:chatbubbles"
          class="text-5xl text-[#7A8C9E] bg-clip-content py-2"
        />
        <h1 class="text-[#7A8C9E] capitalize">All chats</h1>
      </button>
      <button class="py-2 px-5 flex flex-col items-center">
        <Icon
          icon="material-symbols-light:folder"
          class="text-4xl text-[#7A8C9E] bg-clip-content py-1"
        />
        <h1 class="text-[#7A8C9E] capitalize">personel</h1>
      </button>
      <button class="py-2 px-5 flex flex-col items-center">
        <Icon
          icon="material-symbols-light:robot"
          class="text-4xl text-[#7A8C9E] bg-clip-content py-1"
        />
        <h1 class="text-[#7A8C9E] capitalize">bots</h1>
      </button>
      <button class="py-2 px-5 flex flex-col items-center">
        <Icon
          icon="gridicons:speaker"
          class="text-4xl text-[#7A8C9E] bg-clip-content py-1"
        />
        <h1 class="text-[#7A8C9E] capitalize">channels</h1>
      </button>
      <button class="py-2 px-5 flex flex-col items-center">
        <Icon
          icon="bi:people-fill"
          class="text-4xl text-[#7A8C9E] bg-clip-content py-1"
        />
        <h1 class="text-[#7A8C9E] capitalize">groups</h1>
      </button>
      <button class="py-2 px-5 flex flex-col items-center">
        <Icon
          icon="bi:chat-fill"
          class="text-4xl text-[#7A8C9E] bg-clip-content py-1"
        />
        <h1 class="text-[#7A8C9E] capitalize">unread</h1>
      </button>
      <button class="py-2 px-5 flex flex-col items-center">
        <Icon
          icon="material-symbols-light:folder"
          class="text-4xl text-[#7A8C9E] bg-clip-content py-1"
        />
        <h1 class="text-[#7A8C9E] capitalize">VIP TELEGRAM</h1>
      </button>
      <button class="py-2 px-5 flex flex-col items-center">
        <Icon
          icon="bxl:telegram"
          class="text-4xl text-[#7A8C9E] bg-clip-content py-1"
        />
        <h1 class="text-[#7A8C9E] capitalize">Telegram</h1>
      </button>
      <div class="py-2 px-5 flex flex-col items-center">
        <Icon
          icon="akar-icons:two-line-horizontal"
          class="text-4xl text-[#7A8C9E] bg-clip-content py-1"
        />
        <h1 class="text-[#7A8C9E] capitalize">edit</h1>
      </div>
    </div>

    <!-- sidebar hidden -->

    <div
      v-if="showSidebar"
      class="bg-white backdrop w-1/6 absolute pt-4 top-0 left-0 border-r h-screen menu-content duration-1000 ease-in"
    >
      <div class="border-b px-5">
        <img
          src="https://images.unsplash.com/photo-1587590834224-3247f65be147?q=80&w=1000&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8Nnx8Z2lybCUyMGdsYXNzZXN8ZW58MHx8MHx8fDA%3D"
          alt=""
          class="w-12 h-12 rounded-full object-cover"
        />
        <div class="flex justify-between pb-3">
          <div>
            <h1>Mamush Meshesha</h1>
            <p>set emoji status</p>
          </div>
          <Icon icon="ep:arrow-down" />
        </div>
      </div>
      <!-- groups -->
      <div class="px-5">
        <div class="flex gap-3 items-center py-2">
          <Icon icon="ion:people-outline" class="text-3xl" />
          <h1 class="capitalize">new group</h1>
        </div>
        <div class="flex gap-3 items-center py-2">
          <Icon icon="tabler:speakerphone" class="text-3xl" />
          <h1 class="capitalize">new channel</h1>
        </div>
        <div class="flex gap-3 items-center py-2">
          <Icon icon="arcticons:goodwy-contacts" class="text-3xl" />
          <h1 class="capitalize">contacts</h1>
        </div>
        <div class="flex gap-3 items-center py-2">
          <Icon icon="fluent:call-20-regular" class="text-3xl" />
          <h1 class="capitalize">calls</h1>
        </div>
        <div class="flex gap-3 items-center py-2">
          <Icon icon="iconamoon:bookmark-thin" class="text-3xl" />
          <h1 class="capitalize">saved messages</h1>
        </div>
        <div class="flex gap-3 items-center py-2">
          <Icon icon="ep:setting" class="text-3xl" />
          <h1 class="capitalize">settings</h1>
        </div>
        <div class="flex gap-3 items-center py-2">
          <Icon icon="ph:moon-thin" class="text-3xl" />
          <h1 class="capitalize">night mode</h1>
        </div>
      </div>
    </div>

    <!-- end hidden sidebar -->
    <div class="w-full">
      <div class="flex">
        <div class="text-white w-1/4 border-r h-screen overflow-y-scroll">
          <div class="mx-[3%] pt-4">
            <div class="relative">
              <input
                type="search"
                placeholder="Search"
                class="w-full h-11 outline-none border px-4 rounded-full bg-[#bebebe]"
              />
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-9 mt-1 h-9 rounded-full border-4 border-green-700 object-cover z-30 mr-10 absolute top-0 right-0 p-[1px]"
              />
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-9 mt-1 h-9 rounded-full border-4 border-green-700 object-cover z-20 mr-5 absolute top-0 right-0 p-[1px]"
              />
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-9 mt-1 h-9 rounded-full border-4 border-green-700 object-cover z-10 ml-10 absolute top-0 right-0 p-[1px]"
              />
            </div>
          </div>
          <!-- main content -->
          <div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
            <div class="flex gap-3 py-4 items-center px-4">
              <img
                src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                alt=""
                class="w-12 h-12 rounded-full objuct-cover"
              />
              <div>
                <div class="flex gap-2">
                  <Icon icon="gridicons:speaker" class="text-black" />
                  <h1 class="text-black">TIKVAH-SPORT</h1>
                </div>
                <h1 class="text-black">ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር...</h1>
              </div>
            </div>
          </div>
        </div>
        <!-- internal content -->
        <div
          class="w-3/4 h-screen bg-cover object-contain bg-no-repeat"
          :style="{ backgroundImage: `url(${backGround})` }"
        >
          <div>
            <div class="border-b border-t bg-white">
              <div class="relative mx-6 py-2">
                <h1>TIKVAH-SPORT</h1>
                <h1 class="text-sm text-[#bbb8b8]">124,454 subscribers</h1>
                <div class="absolute top-0 right-0 flex gap-5 mt-5 text-2xl">
                  <Icon icon="iconamoon:search-thin" />
                  <Icon icon="system-uicons:pages" />
                  <Icon icon="pepicons-pencil:dots-y" class="font-extrabold" />
                </div>
              </div>
            </div>
            <!-- background -->
            <div class="p-5">
              <div
                class="rounded-2xl border w-[400px] relative h-[590px] bg-white"
              >
                <h1 class="py-2 px-3">TIKVAH-SPORT</h1>
                <img
                  src="https://qph.cf2.quoracdn.net/main-qimg-228f3d607fc97343081cd2ab2798d9fb-lq"
                  alt=""
                  class="h-[300px] w-full object-cover"
                />
                <h1 class="pb-4">
                  ድሬዳዋ ከተማ ድል አድርጓል ! በኢትዮጵያ ፕርሚየር ሊግ የአስረኛ ሳምንት መርሐ ግብር ድሬዳዋ
                  ከተማ ከኢትዮጵያ መድን ጋር ያደረጉትን ጨዋታ 2ለ1 በሆነ ውጤት ማሸነፍ ችለዋል። የድሬዳዋ ከተማን
                  የማሸነፊያ ግቦች ካርሎስ ዳምጠው እና ቻርልስ ሙሴጌ ከመረብ ሲያሳርፉ ለኢትዮጵያ መድን ወገኔ
                  ገዛኸኝ አስቆጥሯል። ድሬዳዋ ከተማ ማሸነፉን ተከትሎ በአስራ አንድ ነጥብ አሴራ አንደኛ ደረጃ ላይ
                  ሲቀመጥ ኢትዮጵያ መድን በዘጠኝ ነጥብ አስራ ሁለተኛ ደረጃን ይዟል።
                </h1>
                <div class="absolute bottom-0 left-0 flex gap-7 my-6">
                  <div class="flex gap-1 items-center">
                    <Icon icon="noto:fire" />
                    <h1>24</h1>
                  </div>
                  <div class="flex gap-1 items-center">
                    <Icon icon="iconamoon:like-thin" />
                    <h1>50</h1>
                  </div>
                  <div class="flex gap-1 items-center">
                    <Icon icon="flat-color-icons:like" />
                    <h1>100</h1>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(10px);
  z-index: 10;
}

.menu-content {
  position: absolute;
  top: 0;
  left: 0;
  width: 20%;
  height: 100%;
  background-color: white;
  z-index: 20;
}
</style>
