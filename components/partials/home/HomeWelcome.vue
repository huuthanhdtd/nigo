<template>
  <div
    class="bg-light-elevatedSurface dark:bg-dark-elevatedSurface shadow-nuxt relative"
  >
    <div class="container mx-auto px-4">
      <div class="flex justify-between py-16 sm:py-24">
        <div
          class="w-full lg:w-1/2 xl:w-6/12 text-center lg:text-left py-4 sm:p-0"
        >
          <!--welcome title i18n -->
          <i18n
            path="homepage.welcome.title"
            tag="h1"
            class="text-4xl xl:text-5xl text-light-onSurfacePrimary dark:text-dark-onSurfacePrimary font-medium tracking-normal leading-tight mb-6"
          >
            <template v-slot:br>
              <br />
            </template>
            <template v-slot:frameworkType>
              <span class="text-nuxt-lightgreen">
                Nigo
              </span>
            </template>
          </i18n>
          <!--welcome description i18n -->
          <i18n
            path="homepage.welcome.description"
            tag="h2"
            class="xl:text-lg text-light-onSurfaceSecondary dark:text-dark-onSurfaceSecondary font-medium leading-relaxed mb-6"
          >
            <template v-slot:openSource>
              <span title="Under MIT license">
                {{ $t('homepage.welcome.openSource') }}
              </span>
            </template>
          </i18n>

          <div
            class="flex flex-col sm:block text-light-onSurfaceSecondary dark:text-dark-onSurfaceSecondary"
            data-cy="newsletter-link"
          >
            <a
              href="#subscribe-to-newsletter"
              class="hover:text-light-onSurfacePrimary dark:hover:text-dark-onSurfacePrimary"
            >
              {{ $t('homepage.welcome.get_updates') }} 💌
            </a>
          </div>
        </div>
        <DesignIllustration
          class="w-2/3 mx-auto lg:mx-0 lg:w-5/12 lg:-mt-8 text-light-elevatedSurface dark:text-dark-elevatedSurface"
        />
      </div>
    </div>
  </div>
</template>

<script>
import DesignIllustration from '~/assets/illustrations/design.svg?inline'

export default {
  components: {
    DesignIllustration
  },
  computed: {
    /**
     * This was done because the vimeo.com site has been blocked in Indonesia.
     * So, the video url is redirected to the youtube.com service.
     *
     * https://github.com/nuxt/nuxtjs.org/pull/661
     */
    videoUrl() {
      return this.$i18n.locale === 'id'
        ? 'https://www.youtube.com/embed/7ITypVi-qRY'
        : 'https://player.vimeo.com/video/311756540'
    }
  }
}
</script>
