<template>
  <div class="shadow-nuxt">
    <div class="container mx-auto px-4 pt-16 pb-12">
      <div class="flex flex-wrap justify-between mb-8">
        <div class="lg:w-6/12 lg:text-left text-center p-4 sm:p-0">
          <i18n
            path="team.title"
            tag="h1"
            class="text-3xl xl:text-4xl text-light-onSurfacePrimary dark:text-dark-onSurfacePrimary font-medium leading-normal mb-6 lg:pt-4 transition-colors duration-300 ease-linear"
          >
            {{ $t('team.title') }}
            <template v-slot:nuxt>
              <AppTitle />
            </template>
          </i18n>
          <h3
            class="xl:text-lg text-light-onSurfaceSecondary dark:text-dark-onSurfaceSecondary font-medium leading-relaxed mb-6"
          >
            {{ $t('team.description') }}
          </h3>
        </div>
        <TeamIllustration
          class="w-2/3 mx-auto lg:mx-0 lg:w-5/12 lg:-mt-8 text-light-elevatedSurface dark:text-dark-elevatedSurface"
        />

        <TeamMembers :team="nuxtCompany.team" :title="nuxtCompany.title" />
      </div>
    </div>
  </div>
</template>

<script>
import TeamIllustration from '~/assets/illustrations/team.svg?inline'

export default {
  components: {
    TeamIllustration
  },
  data() {
    return {
      nuxtCompany: {
        title: 'Nigo Company',
        team: [
          {
            name: 'Alexandre Chopin',
            city: 'Bordeaux, France',
            github: 'alexchopin',
            twitter: 'iamnuxt',
            website: 'https://alexchopin.com',
            role: 'CEO',
            badges: ['framework']
          },
          {
            name: 'Sébastien Chopin',
            city: 'Bordeaux, France',
            github: 'Atinux',
            twitter: 'Atinux',
            website: 'https://atinux.com',
            role: 'CTO',
            badges: ['framework']
          },
          {
            name: 'Pooya Parsa',
            alias: 'پویا پارسا',
            city: 'Amsterdam, Netherlands',
            github: 'pi0',
            twitter: '_pi0_',
            role: 'Head of Framework',
            badges: ['framework']
          },
          {
            name: "Debbie O'Brien",
            city: 'Palma de Mallorca, Spain',
            github: 'debs-obrien',
            twitter: 'debs_obrien',
            website: 'https://debbie.codes',
            role: 'Head of Learning'
          },
          {
            name: 'Florent Delerue',
            city: 'Bordeaux, France',
            github: 'Flosciante',
            twitter: 'flosciante',
            role: 'Chief Process Officer'
          },
          {
            name: 'Sergey Bedritsky',
            city: 'Kiev, Ukraine',
            github: 'bdrtsky',
            twitter: 'sergeybedritsky',
            website: 'https://sergeybedritsky.me/',
            role: 'Lead Developer'
          },
          {
            name: 'Vincent Rodriguez',
            city: 'Bordeaux, France',
            github: 'R-mooon',
            twitter: 'RodrigodelaNoch',
            role: 'Creative Developer'
          },
          {
            name: 'Sarah Moriceau',
            city: 'Bordeaux, France',
            github: 'sarahnuxtjs',
            twitter: 'moriceau_sarah',
            role: 'Web Designer'
          },
          {
            name: 'Benjamin Canac',
            city: 'Bordeaux, France',
            github: 'benjamincanac',
            twitter: 'benjamincanac',
            role: 'Back-end developer'
          },
          {
            name: 'Ahad Birang',
            city: 'Tehran, Iran',
            github: 'farnabaz',
            twitter: 'a_birang',
            website: 'https://farnabaz.ir',
            role: 'Lead developer'
          }
        ]
      }
    }
  },
  head() {
    const title = this.$t('team.meta.title')
    const description = this.$t('team.meta.description')

    return {
      title,
      meta: [
        { hid: 'description', name: 'description', content: description },
        // Open Graph
        { hid: 'og:title', property: 'og:title', content: title },
        {
          hid: 'og:description',
          property: 'og:description',
          content: description
        },
        // Twitter Card
        { hid: 'twitter:title', name: 'twitter:title', content: title },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: description
        }
      ]
    }
  }
}
</script>
