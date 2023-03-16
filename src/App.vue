<template>
  <div class="sticky top-0 z-10 shadow-md">
    <div class="relative bg-purple-900">
      <div class="max-w-full flex justify-between items-center py-3 px-3 sm:px-6 lg:px-8">
        <div class="flex items-center space-x-4">
          <FacebookIcon class="w-6 h-6 fill-white" />
          <EnvelopeIcon class="w-6 h-6 text-white" />
        </div>
        <div class="flex items-center space-x-4  text-white font-semibold">
          <span class="tracking-tight">ΣΚΛΕΙΣΤΕ ΡΑΝΤΕΒΟΥ ΤΩΡΑ</span>
          <span class="tracking-tight">210 222 0544</span>
        </div>
      </div>
    </div>

    <nav class="w-full">
      <Popover class="relative w-full bg-white">
        <div class="w-full flex items-center px-4 py-6 sm:px-6 md:justify-start md:space-x-10 lg:px-8">
          <div class="lg:w-0 lg:flex-1">
            <a href="/" class="flex items-center space-x-2">
              <ToothIcon class="w-auto h-8 sm:h-10 fill fill-purple-600" />
              <span class="text-neutral-900 font-bolt text-xl sm:text-3xl tracking-tight">DentAll</span>
            </a>
          </div>

          <div class="-my-2 -mr-2 md:hidden">
            <PopoverButton class="inline-flex items-center justify-center rounded-md bg-white p-2 text-neutral-400 hover:bg-neutral-100 hover:text-neutral-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-purple-500">
              <Bars3Icon class="h-6 w-6" aria-hidden="true" />
            </PopoverButton>
          </div>

          <PopoverGroup as="nav" class=" hidden space-x-10 md:flex">
            <a href="#" class="text-base font-medium text-neutral-500 hover:text-neutral-900 uppercase">Αρχική</a>
            <Popover class="relative" v-slot="{ open }">
              <PopoverButton :class="[open ? 'text-neutral-900' : 'text-neutral-500', 'group inline-flex items-center rounded-md bg-white text-base font-medium hover:text-neutral-900 focus:outline-none focus:ring-2 focus:ring-purple-500 focus:ring-offset-2']">
                <span class="uppercase">Το Ιατρείο μας</span>
                <ChevronDownIcon :class="[open ? 'text-neutral-600' : 'text-neutral-400', 'ml-2 h-5 w-5 group-hover:text-neutral-500']" aria-hidden="true" />
              </PopoverButton>

              <transition enter-active-class="transition ease-out duration-200" enter-from-class="opacity-0 translate-y-1" enter-to-class="opacity-100 translate-y-0" leave-active-class="transition ease-in duration-150" leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 translate-y-1">
                <PopoverPanel class="absolute z-10 -ml-4 mt-3 w-screen max-w-md transform lg:left-1/2 lg:ml-0 lg:max-w-2xl lg:-translate-x-1/2">
                  <div class="overflow-hidden rounded-lg shadow-lg ring-1 ring-black ring-opacity-5">
                    <div class="relative grid gap-6 bg-white px-5 py-6 sm:gap-8 sm:p-8 lg:grid-cols-2">
                      <a v-for="item in solutions" :key="item.name" :href="item.href" class="-m-3 flex items-start rounded-lg p-3 hover:bg-neutral-50">
                        <div class="flex h-10 w-10 flex-shrink-0 items-center justify-center rounded-md bg-purple-600 text-white sm:h-12 sm:w-12">
                          <component :is="item.icon" class="h-6 w-6" aria-hidden="true" />
                        </div>
                        <div class="ml-4">
                          <p class="text-base font-medium text-neutral-900">{{ item.name }}</p>
                          <p class="mt-1 text-sm text-neutral-500">{{ item.description }}</p>
                        </div>
                      </a>
                    </div>
                  </div>
                </PopoverPanel>
              </transition>
            </Popover>

            <a href="#" class="text-base font-medium text-neutral-500 hover:text-neutral-900 uppercase">Υπηρεσίες</a>
            <a href="#" class="text-base font-medium text-neutral-500 hover:text-neutral-900 uppercase">Η ομάδα μας</a>
            <a href="#" class="text-base font-medium text-neutral-500 hover:text-neutral-900 uppercase">Άρθρα</a>
            <a href="#" class="text-base font-medium text-neutral-500 hover:text-neutral-900 uppercase">Συνεχείς Ερωτήσεις</a>
            <a href="#" class="text-base font-medium text-neutral-500 hover:text-neutral-900 uppercase">Επικοινωνία</a>
          </PopoverGroup>

          <div class="mr-auto hidden items-center justify-end md:flex md:flex-1 lg:w-0">
            <!-- Spacer -->
            <!-- <a href="#" class="whitespace-nowrap text-base font-medium text-neutral-500 hover:text-neutral-900">Sign in</a>
            <a href="#" class="ml-8 inline-flex items-center justify-center whitespace-nowrap rounded-md border border-transparent bg-purple-600 bg-origin-border px-4 py-2 text-base font-medium text-white shadow-sm hover:from-purple-700 hover:to-purple-700">Sign up</a> -->
          </div>
        </div>

        <transition enter-active-class="duration-200 ease-out" enter-from-class="opacity-0 scale-95" enter-to-class="opacity-100 scale-100" leave-active-class="duration-100 ease-in" leave-from-class="opacity-100 scale-100" leave-to-class="opacity-0 scale-95">
          <PopoverPanel focus class="absolute inset-x-0 top-0 z-30 origin-top-right transform p-2 transition md:hidden">
            <div class="divide-y-2 divide-neutral-50 rounded-lg bg-white shadow-lg ring-1 ring-black ring-opacity-5">
              <div class="px-5 pt-5 pb-6">
                <div class="flex items-center justify-between">
                  <div>
                    <img class="h-8 w-auto" src="https://tailwindui.com/img/logos/mark.svg" alt="Your Company" />
                  </div>

                  <div class="-mr-2">
                    <PopoverButton class="inline-flex items-center justify-center rounded-md bg-white p-2 text-neutral-400 hover:bg-neutral-100 hover:text-neutral-500 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-purple-500">
                      <span class="sr-only">Close menu</span>
                      <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                    </PopoverButton>
                  </div>
                </div>

                <div class="mt-6">
                  <nav class="grid grid-cols-1 gap-7">
                    <a v-for="item in solutions" :key="item.name" :href="item.href" class="-m-3 flex items-center rounded-lg p-3 hover:bg-neutral-50">
                      <div class="flex h-10 w-10 flex-shrink-0 items-center justify-center rounded-md bg-purple-600 text-white">
                        <component :is="item.icon" class="h-6 w-6" aria-hidden="true" />
                      </div>
                      <div class="ml-4 text-base font-medium text-neutral-900">{{ item.name }}</div>
                    </a>
                  </nav>
                </div>
              </div>

              <div class="py-6 px-5">
                <div class="grid grid-cols-2 gap-4">
                  <a href="#" class="text-base font-medium text-neutral-900 hover:text-neutral-700">Pricing</a>
                  <a href="#" class="text-base font-medium text-neutral-900 hover:text-neutral-700">Partners</a>
                  <a href="#" class="text-base font-medium text-neutral-900 hover:text-neutral-700">Company</a>
                </div>

                <!-- <div class="mt-6">
                  <a href="#" class="flex w-full items-center justify-center rounded-md border border-transparent bg-purple-600 bg-origin-border px-4 py-2 text-base font-medium text-white shadow-sm hover:from-purple-700 hover:to-purple-700">Sign up</a>
                  <p class="mt-6 text-center text-base font-medium text-neutral-500">
                    Existing customer?
                    <a href="#" class="text-neutral-900">Sign in</a>
                  </p>
                </div> -->
              </div>
            </div>
          </PopoverPanel>
        </transition>
      </Popover>
    </nav>
  </div>

  <header class="relative overflow-hidden bg-white">
    <div class="mx-auto max-w-7xl">
      <main class="mx-auto my-10 max-w-7xl px-4 sm:mt-12 sm:px-6 md:my-16 lg:my-20 lg:px-8 xl:my-28">
        <div class="sm:text-center lg:text-left">
          <h1 class="text-4xl font-bold tracking-tight text-neutral-900 sm:text-5xl md:text-6xl">
            <span class="block xl:inline text-neutral-900 tracking-tight">DentAll</span><br>
            <span class="block text-purple-600 xl:inline text-2xl md:text-5xl tracking-tight">Για Λαμπερά Δόντια!</span>
          </h1>
          <p class="mt-2 text-base text-neutral-500 sm:mx-auto sm:mt-5 sm:max-w-xl sm:text-lg md:mt-5 md:text-xl lg:mx-0 tracking-tight">Στο οδοντιατρείο μας σας προσφέρουμε ένα λαμπερό χαμόγελο όχι στη βάση ενός τρόπο ζωής αλλά στη βάση γερών ούλων και δοντιών. Ξεκινάμε πάντα από την υγεία του στόματος για να καταλήξουμε στην ομορφιά!</p>
          <div class="mt-5 sm:mt-8 sm:flex sm:justify-center lg:justify-start">
            <div class="rounded-md shadow">
              <a href="#" class="flex w-full items-center justify-center rounded-md bg-purple-600 px-8 py-3 text-base font-medium text-neutral-100 hover:bg-purple-700 md:py-4 md:px-10 md:text-lg uppercase">
                ΕΠΙΚΟΙΝΩΝΗΣΤΕ ΜΑΖΙ ΜΑΣ
              </a>
            </div>
          </div>
        </div>
      </main>
    </div>
    <div class="lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2">
      <img class="w-full h-96 lg:h-full object-cover" src="https://images.unsplash.com/photo-1626736985932-c0df2ae07a2e" alt="" />
    </div>
  </header>

  <section class="mx-auto max-w-7xl py-20 ">
    <h1 class="text-center text-neutral-900 text-3xl py-10">ΠΑΡΟΧΕΣ & ΥΠΗΡΕΣΙΕΣ</h1>

    <div class="flex flex-wrap justify-center items-center gap-6 px-10 sm:px-0">
      <div v-for="(service, index) in services" :key="index" class="w-full sm:w-1/2 md:w-1/3 bg-purple-100 rounded-md p-4">
        <div class="max-w-fit bg-purple-300 px-6 py-4 rounded-full">
          <component :is="service.icon" class="w-auto h-10 fill-purple-900" />
        </div>

        <div class="mt-10 flex-1">
          <h3 class="text-neutral-900 text-3xl tracking-tight">{{ service.title }}</h3>
          <p class="mt-2 text-neutral-500 tracking-tight">{{ service.content }}</p>
        </div>
        
        <a :href="service.href" class="group mt-4 flex flex-1 items-center space-x-2">
          <span class="text-neutral-900 text-md group-hover:text-purple-600 transition duration-300">Περισσότερα</span>
          <ArrowLongRightIcon class="w-6 h-6 text-neutral-900 group-hover:text-purple-600 transition duration-300" />
        </a>
      </div>
    </div>
  </section>

  <section class="h-[450px] bg-[url(http://www.dentall.gr/images/background/5.jpg?v=2)] bg-fixed bg-center bg-no-repeat bg-cover">
    <div class="min-h-full flex items-center justify-center bg-purple-600/30">
      <div class="max-w-3xl px-10 py-12">
        <div class="flex justify-center items-center space-x-2">
          <ToothIcon class="w-auto h-10 sm:h-14 fill fill-neutral-100" />
          <span class="text-neutral-100 font-bolt text-xl sm:text-4xl tracking-tight">DentAll</span>
        </div>
        <p class="mt-2 text-4xl text-neutral-100 tracking-tight">ΠΑΡΟΧΗ ΠΟΙΟΤΙΚΩΝ ΟΔΟΝΤΙΑΤΡΙΚΩΝ ΥΠΗΡΕΣΙΩΝ ΓΙΑ ΟΛΗ ΤΗΝ ΟΙΚΟΓΕΝΕΙΑ </p>
      </div>
    </div>
  </section>

  <section class="mx-auto max-w-7xl py-20">
    <h1 class="text-center text-neutral-900 text-3xl py-10">Η ΟΜΑΔΑ ΜΑΣ</h1>

    <div class="flex flex-wrap justify-center items-center gap-6 px-10 sm:px-0">
      <div v-for="(person, index) in people" :key="index" class="w-full sm:w-1/2 md:w-1/3 bg-purple-100 rounded-md py-4">
        <img :src="person.image" class="mx-auto w-auto h-60" />

        <div class="mt-6">
          <h3 class="text-neutral-900 text-2xl tracking-tight text-center">{{ person.name }}</h3>
        </div>
        
        <a :href="person.href" class="group mt-2 flex justify-center items-center space-x-2">
          <span class="text-neutral-900 text-lg group-hover:text-purple-600 transition duration-300">{{ person.major }}</span>
          <ArrowLongRightIcon class="w-6 h-6 text-neutral-900 group-hover:text-purple-600 transition duration-300" />
        </a>
      </div>
    </div>
  </section>

  <section class="relative">
    <div class="relative mx-auto max-w-7xl lg:grid lg:grid-cols-5">
      <div class="py-10 px-4 sm:px-6 lg:col-span-2 lg:px-8 lg:pt-24 lg:pb-8 xl:pr-12">
        <div class="mx-auto max-w-lg">
          <h2 class="text-2xl font-bold tracking-tight text-neutral-900 sm:text-3xl">Ελάτε Σε Επαφή</h2>
          <dl class="mt-8 text-base text-neutral-500">
            <div>
              <dd class="flex">
                <BuildingOfficeIcon class="h-6 w-6 flex-shrink-0 text-neutral-400" aria-hidden="true" />
                <div class="ml-3">
                  <p>Ωρωπού 64, Γαλάτσι</p>
                  <p>11146, Αθήνα</p>
                </div>
              </dd>
            </div>
            <div class="mt-6">
              <dd class="flex">
                <PhoneIcon class="h-6 w-6 flex-shrink-0 text-neutral-400" aria-hidden="true" />
                <span class="ml-3">210 2220544</span>
              </dd>
            </div>
            <div class="mt-3">
              <dd class="flex">
                <EnvelopeIcon class="h-6 w-6 flex-shrink-0 text-neutral-400" aria-hidden="true" />
                <span class="ml-3">info@dentall.gr</span>
              </dd>
            </div>
          </dl>
          <div class="mt-6">
            <iframe class="w-96 h-96 border-0 focus:border-0" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3143.085443124494!2d23.7485055!3d38.021787499999995!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x14a1a28faa981ee9%3A0xcda65c7c02b0c36f!2sOropou%2064%2C%20Galatsi%20111%2046!5e0!3m2!1sen!2sgr!4v1678890750070!5m2!1sen!2sgr" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
          </div>
        </div>
      </div>
      <div class="py-10 px-4 sm:px-6 lg:col-span-3 lg:pt-24 lg:pb-8 lg:px-8 xl:pl-12">
        <div class="mx-auto max-w-lg lg:max-w-none">
          <form class="grid grid-cols-1 gap-y-6">
            <div>
              <label for="full-name" class="block text-md font-semibold leading-6 text-neutral-700">Ονοματεπώνυμο<span class="text-red-600">*</span></label>
              <input type="text" name="full-name" id="full-name" autocomplete="name" required class="mt-1 block w-full rounded-md border-neutral-300 py-3 px-4 shadow-sm focus:border-purple-500 focus:ring-purple-500" />
            </div>
            <div>
              <label for="phone" class="block text-md font-semibold leading-6 text-neutral-700">Αριθμός Τηλεφώνου<span class="text-red-600">*</span></label>
              <input type="text" name="phone" id="phone" autocomplete="tel" required class="mt-1 block w-full rounded-md border-neutral-300 py-3 px-4 shadow-sm focus:border-purple-500 focus:ring-purple-500" />
            </div>
            <div>
              <label for="message" class="block text-md font-semibold leading-6 text-neutral-700">Μάνυμα<span class="text-red-600">*</span></label>
              <textarea id="message" name="message" rows="6" required class="mt-1 block w-full rounded-md border-neutral-300 py-3 px-4 shadow-sm focus:border-purple-500 focus:ring-purple-500" />
            </div>
            <div>
              <button class="inline-flex justify-center rounded-md border border-transparent bg-purple-600 py-3 px-6 text-base font-medium text-white shadow-sm hover:bg-purple-700 focus:outline-none focus:ring-2 focus:ring-purple-500 focus:ring-offset-2">Submit</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>

  <footer aria-labelledby="footer-heading">
    <div class="mx-auto max-w-7xl pt-8 pb-12 px-4 sm:px-6 lg:py-16 lg:px-8">
      <div class="mt-8 border-t border-neutral-200 pt-8 md:flex md:items-center md:justify-between">
        <div class="flex space-x-6 md:order-2">
          <a v-for="item in social" :key="item.name" :href="item.href" class="text-neutral-400 hover:text-neutral-500">
            <span class="sr-only">{{ item.name }}</span>
            <component :is="item.icon" class="h-6 w-6" aria-hidden="true" />
          </a>
        </div>
        <p class="mt-8 text-base text-neutral-400 md:order-1 md:mt-0">&copy; {{ new Date().getFullYear() }} DenAll, Inc. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { ref, defineComponent, h } from 'vue'
import {
  Popover,
  PopoverGroup,
  PopoverButton,
  PopoverPanel,
} from '@headlessui/vue'
import {
  Bars3Icon,
  XMarkIcon,
  InboxIcon,
  ChatBubbleBottomCenterTextIcon,
  ChatBubbleLeftRightIcon,
  QuestionMarkCircleIcon,
  EnvelopeIcon,
  ArrowLongRightIcon,
  PhoneIcon,
  BuildingOfficeIcon,
} from '@heroicons/vue/24/outline'
import {
  ChevronDownIcon,
  HeartIcon
} from '@heroicons/vue/20/solid'
import FacebookIcon from '@/components/Icons/FacebookIcon.vue'
import ToothIcon from '@/components/Icons/ToothIcon.vue'
import ChildReachingIcon from '@/components/Icons/ChildReachingIcon.vue'
import TeethIcon from '@/components/Icons/TeethIcon.vue'
import ShieldIcon from '@/components/Icons/ShieldIcon.vue'

const solutions = [
  {
    name: 'Inbox',
    description: 'Get a better understanding of where your traffic is coming from.',
    href: '#',
    icon: InboxIcon,
  },
  {
    name: 'Messaging',
    description: 'Speak directly to your customers in a more meaningful way.',
    href: '#',
    icon: ChatBubbleBottomCenterTextIcon,
  },
  {
    name: 'Live Chat',
    description: "Your customers' data will be safe and secure.",
    href: '#',
    icon: ChatBubbleLeftRightIcon,
  },
  {
    name: 'Knowledge Base',
    description: "Connect with third-party tools that you're already using.",
    href: '#',
    icon: QuestionMarkCircleIcon,
  },
]

const services = [
  {
    icon: ToothIcon,
    title: 'Αποκατάσταση',
    content: 'Σχεδιάζουμε πάντα την αποκατάσταση του στόματος με βάση την επιστήμη.',
    href: '#'
  },
  {
    icon: TeethIcon,
    title: 'Ορθοδοντική',
    content: 'Προσφέρουμε ολοκληρωμένη ορθοδοντική θεραπεία και φροντίδα.',
    href: '#'
  },
  {
    icon: ChildReachingIcon,
    title: 'Παιδοδοντία',
    content: 'Με σύμμαχο την πολυετή εξειδίκευση και εμπειρία σε παιδιά και εφήβους.',
    href: '#'
  },
  {
    icon: ShieldIcon,
    title: 'Αθλητικοί Νάρθηκες',
    content: 'Προσπαθούμε να ευαισθητοποιήσουμε αθλητές, γονείς και δασκάλους.',
    href: '#'
  }
]

const people = [
  {
    image: 'http://www.dentall.gr/images/team/01.png',
    name: 'Γρηγόρης Γρηγοράκης',
    major: 'Παιδοδοντίατρος',
    href: '#'
  },
  {
    image: 'http://www.dentall.gr/images/team/02.png',
    name: 'Γιάννης Τράπαλης',
    major: 'Οδοντίατρος',
    href: '#'
  },
  {
    image: 'http://www.dentall.gr/images/team/03.png',
    name: 'Βασίλης Καλαμάτας',
    major: 'Ορθοδοντικός',
    href: '#'
  },
  {
    image: 'http://www.dentall.gr/images/team/04.png',
    name: 'Τζώρτζια Μακρυγιάννη',
    major: 'Οδοντίατρος',
    href: '#'
  }
]

const social = [
  {
    name: 'Facebook',
    href: '#',
    icon: defineComponent({
      render: () =>
        h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
          h('path', {
            'fill-rule': 'evenodd',
            d: 'M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V12h2.54V9.797c0-2.506 1.492-3.89 3.777-3.89 1.094 0 2.238.195 2.238.195v2.46h-1.26c-1.243 0-1.63.771-1.63 1.562V12h2.773l-.443 2.89h-2.33v6.988C18.343 21.128 22 16.991 22 12z',
            'clip-rule': 'evenodd',
          }),
        ]),
    }),
  },
  {
    name: 'Instagram',
    href: '#',
    icon: defineComponent({
      render: () =>
        h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
          h('path', {
            'fill-rule': 'evenodd',
            d: 'M12.315 2c2.43 0 2.784.013 3.808.06 1.064.049 1.791.218 2.427.465a4.902 4.902 0 011.772 1.153 4.902 4.902 0 011.153 1.772c.247.636.416 1.363.465 2.427.048 1.067.06 1.407.06 4.123v.08c0 2.643-.012 2.987-.06 4.043-.049 1.064-.218 1.791-.465 2.427a4.902 4.902 0 01-1.153 1.772 4.902 4.902 0 01-1.772 1.153c-.636.247-1.363.416-2.427.465-1.067.048-1.407.06-4.123.06h-.08c-2.643 0-2.987-.012-4.043-.06-1.064-.049-1.791-.218-2.427-.465a4.902 4.902 0 01-1.772-1.153 4.902 4.902 0 01-1.153-1.772c-.247-.636-.416-1.363-.465-2.427-.047-1.024-.06-1.379-.06-3.808v-.63c0-2.43.013-2.784.06-3.808.049-1.064.218-1.791.465-2.427a4.902 4.902 0 011.153-1.772A4.902 4.902 0 015.45 2.525c.636-.247 1.363-.416 2.427-.465C8.901 2.013 9.256 2 11.685 2h.63zm-.081 1.802h-.468c-2.456 0-2.784.011-3.807.058-.975.045-1.504.207-1.857.344-.467.182-.8.398-1.15.748-.35.35-.566.683-.748 1.15-.137.353-.3.882-.344 1.857-.047 1.023-.058 1.351-.058 3.807v.468c0 2.456.011 2.784.058 3.807.045.975.207 1.504.344 1.857.182.466.399.8.748 1.15.35.35.683.566 1.15.748.353.137.882.3 1.857.344 1.054.048 1.37.058 4.041.058h.08c2.597 0 2.917-.01 3.96-.058.976-.045 1.505-.207 1.858-.344.466-.182.8-.398 1.15-.748.35-.35.566-.683.748-1.15.137-.353.3-.882.344-1.857.048-1.055.058-1.37.058-4.041v-.08c0-2.597-.01-2.917-.058-3.96-.045-.976-.207-1.505-.344-1.858a3.097 3.097 0 00-.748-1.15 3.098 3.098 0 00-1.15-.748c-.353-.137-.882-.3-1.857-.344-1.023-.047-1.351-.058-3.807-.058zM12 6.865a5.135 5.135 0 110 10.27 5.135 5.135 0 010-10.27zm0 1.802a3.333 3.333 0 100 6.666 3.333 3.333 0 000-6.666zm5.338-3.205a1.2 1.2 0 110 2.4 1.2 1.2 0 010-2.4z',
            'clip-rule': 'evenodd',
          }),
        ]),
    }),
  },
  {
    name: 'Twitter',
    href: '#',
    icon: defineComponent({
      render: () =>
        h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
          h('path', {
            d: 'M8.29 20.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0022 5.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.072 4.072 0 012.8 9.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 012 18.407a11.616 11.616 0 006.29 1.84',
          }),
        ]),
    }),
  },
  {
    name: 'GitHub',
    href: '#',
    icon: defineComponent({
      render: () =>
        h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
          h('path', {
            'fill-rule': 'evenodd',
            d: 'M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z',
            'clip-rule': 'evenodd',
          }),
        ]),
    }),
  },
  {
    name: 'Dribbble',
    href: '#',
    icon: defineComponent({
      render: () =>
        h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
          h('path', {
            'fill-rule': 'evenodd',
            d: 'M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10c5.51 0 10-4.48 10-10S17.51 2 12 2zm6.605 4.61a8.502 8.502 0 011.93 5.314c-.281-.054-3.101-.629-5.943-.271-.065-.141-.12-.293-.184-.445a25.416 25.416 0 00-.564-1.236c3.145-1.28 4.577-3.124 4.761-3.362zM12 3.475c2.17 0 4.154.813 5.662 2.148-.152.216-1.443 1.941-4.48 3.08-1.399-2.57-2.95-4.675-3.189-5A8.687 8.687 0 0112 3.475zm-3.633.803a53.896 53.896 0 013.167 4.935c-3.992 1.063-7.517 1.04-7.896 1.04a8.581 8.581 0 014.729-5.975zM3.453 12.01v-.26c.37.01 4.512.065 8.775-1.215.25.477.477.965.694 1.453-.109.033-.228.065-.336.098-4.404 1.42-6.747 5.303-6.942 5.629a8.522 8.522 0 01-2.19-5.705zM12 20.547a8.482 8.482 0 01-5.239-1.8c.152-.315 1.888-3.656 6.703-5.337.022-.01.033-.01.054-.022a35.318 35.318 0 011.823 6.475 8.4 8.4 0 01-3.341.684zm4.761-1.465c-.086-.52-.542-3.015-1.659-6.084 2.679-.423 5.022.271 5.314.369a8.468 8.468 0 01-3.655 5.715z',
            'clip-rule': 'evenodd',
          }),
        ]),
    }),
  },
]
</script>
