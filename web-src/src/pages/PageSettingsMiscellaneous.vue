<template>
  <div class="fd-page-with-tabs">
    <tabs-settings />
    <content-with-heading>
      <template #heading-left>
        <div
          class="title is-4"
          v-text="$t('page.settings.miscellaneous.streaming.title')"
        />
      </template>
      <template #content>
        <settings-checkbox category="misc" name="streamurl_ignore">
          <template #label>
            <span v-text="$t('page.settings.miscellaneous.streaming.ignore')" />
          </template>
        </settings-checkbox>
        <settings-textfield
          category="misc"
          name="streamurl_keywords_artwork_url"
          :placeholder="$t('page.settings.miscellaneous.streaming.keywords')"
        >
          <template #label>
            <span
              v-text="$t('page.settings.miscellaneous.streaming.keywords')"
            />
          </template>
        </settings-textfield>
        <settings-textfield
          category="misc"
          name="streamurl_keywords_length"
          :placeholder="$t('page.settings.miscellaneous.streaming.keywords-length')"
        >
          <template #label>
            <span
              v-text="$t('page.settings.miscellaneous.streaming.keywords-length')"
            />
          </template>
        </settings-textfield>
      </template>
    </content-with-heading>
  </div>
</template>

<script>
import ContentWithHeading from '@/templates/ContentWithHeading.vue'
import SettingsCheckbox from '@/components/SettingsCheckbox.vue'
import SettingsTextfield from '../components/SettingsTextfield.vue'
import TabsSettings from '@/components/TabsSettings.vue'
import { useServicesStore } from '@/stores/services'

export default {
  name: 'PageSettingsMiscellaneous',
  components: {
    ContentWithHeading,
    SettingsCheckbox,
    SettingsTextfield,
    TabsSettings
  },

  setup() {
    return { servicesStore: useServicesStore() }
  },

  computed: {
    spotify() {
      return this.servicesStore.spotify
    }
  }
}
</script>
