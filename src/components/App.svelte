<!-- App.svelte -->
<App params={f7params} themeDark={$settingsData.enableDarkMode}>

{#if develMode}
  <View main url="/{develPage}"/>
{:else}
  <View main url="/"/>
{/if}

</App>

<script>
  // Import pages components
  import { onMount } from 'svelte';
  import cordovaApp from '../js/cordova-app';
  import CollectionListView from '../views/CollectionListView.svelte';
  import CategoryListView from '../views/CategoryListView.svelte';
  import SettingsView from '../views/SettingsView.svelte';
  import { downloadedCollections } from '../js/store.js';
  import { f7, f7ready, App, Views, View } from 'framework7-svelte';
  import { Device }  from 'framework7/framework7-lite.esm.bundle.js';
  import localforage from "localforage";
  import cordovaSQLiteDriver from "localforage-cordovasqlitedriver";

  import { waitLocale, addMessages, init, getLocaleFromNavigator } from 'svelte-i18n';
  import en from '../localization/en.json';
  import cs from '../localization/cs.json';
  import { appName, appId, develMode, develPage } from '../js/config.js';
  import { settingsData } from '../js/store.js';

  import { 
    collectionData,
    categoryData, 
    categoryDetailData,
    trainingData,
    statisticsData
  } from '../js/store.js';


  // internationalization init:
  export async function preload() {
    addMessages('en', en);
    addMessages('cs', cs);
    init({
      fallbackLocale: 'cs',
      initialLocale: getLocaleFromNavigator(),
    })
    return waitLocale()
  }
  preload();

  onMount(() => {
    f7ready(() => {
      // cordova app init:
      cordovaApp.init(f7);

    });
  })

  // framework7 init:
  const f7params = {
    id: appId,
    name: appName,
    theme: 'auto', // Automatic theme detection
    input: {
      scrollIntoViewOnFocus: Device.cordova && !Device.electron,
      scrollIntoViewCentered: Device.cordova && !Device.electron,
    },
    // Cordova Statusbar settings
    statusbar: {
      overlay: true,
      iosOverlaysWebView: true,
      androidOverlaysWebView: false,
      iosTextColor: "white",
      androidTextColor: "white",
      androidBackgroundColor: "#0F51AB",
      iosBackgroundColor: "#0F51AB",
    },
    routes: [
      {
        path: '/',
        component: CollectionListView
      },
      {
        path: '/CollectionList',
        component: CollectionListView
      },
      {
        path: '/CategoryList',
        component: CategoryListView
      },
      {
        path: '/Settings',
        component: SettingsView
      }
    ]
  };
</script>
