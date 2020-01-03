<template>
  <div class="text-gray-900 mx-12 my-12">
    <nav class="flex font-mono text-6xl text-5 mb-8 text-gray-200">
      <div
        v-for="(links, index) in links"
        :key="index"
        @mouseover="setActiveLinksIndex(index)"
        :class="{ 'text-gray-900': activeLinksIndex === index }"
        class="px-5 first:-ml-5 pt-3 -mt-3 mb-3 transition cursor-default">
        {{ index }}
      </div>
    </nav>
    <ul>
      <li v-for="link in links[activeLinksIndex]" :key="link">
        <a :href="link.link" class="py-1 inline-block transition border-b-2 border-transparent hover:border-gray-900">
          {{ link.label }}
          <span class="text-gray-500 transition">{{ link.link }}</span>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: () => ({
    activeLinksIndex: 0,
    links: [
      [
        { label: 'Facebook', link: 'https://web.facebook.com' },
        { label: 'Gmail', link: 'https://mail.google.com/' },
        { label: 'GitHub', link: 'https://github.com/' },
        { label: 'Keep', link: 'https://keep.google.com' },
        { label: 'Drive', link: 'https://drive.google.com/drive/' },
        { label: 'Photos', link: 'https://photos.google.com/' },
      ],
      [
        { label: 'Youtube', link: 'https://www.youtube.com' },
        { label: 'Sound Cloud', link: 'https://soundcloud.com/stream' },
        { label: 'Spotify', link: 'https://open.spotify.com/collection' },
      ],
      [
        { label: 'Hacker News', link: 'https://news.ycombinator.com' },
        { label: 'The Radavist', link: 'http://theradavist.com' },
        { label: 'Apartment Theraphy', link: 'http://www.apartmenttherapy.com' },
        { label: 'The Setup', link: 'https://usesthis.com' },
        { label: 'KTT', link: 'http://www.kanyetothe.com/forum/' },
      ],
      [
        { label: 'Figma', link: 'https://www.figma.com/files/recent' },
        { label: 'Unsplash', link: 'https://unsplash.com/' },
        { label: 'Straightline', link: 'http://bm.straightline.jp' },
        { label: 'Siiimple', link: 'https://siiimple.com/' },
        { label: 'Behance', link: 'https://www.behance.net/' },
        { label: 'Google Fonts', link: 'https://fonts.google.com/' },
        { label: 'Lorem ipsum', link: 'https://loremipsum.io/' },
      ],
      [
        { label: 'r/OnePiece', link: 'https://www.reddit.com/r/OnePiece' },
        { label: 'r/webdev', link: 'https://www.reddit.com/r/webdev' },
        { label: 'r/Dota2', link: 'https://www.reddit.com/r/Dota2' },
      ],
      [
        { label: '/g/', link: 'https://boards.4chan.org/g/' },
        { label: '/ic/', link: 'https://boards.4chan.org/ic/' },
        { label: '/p/', link: 'https://boards.4chan.org/p/' },
        { label: '/biz/', link: 'https://boards.4chan.org/biz/' },
      ],
    ],
  }),
  methods: {
    setActiveLinksIndex (index) {
      this.activeLinksIndex = index
    },
  },
}
</script>

<style scoped>
  .transition {
    transition: all 250ms ease-in-out;
  }
</style>
