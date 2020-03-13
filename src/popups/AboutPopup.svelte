<Popup class={name} animate={true} >
  <Page>
    <Header type="popup" popupName={name} title={$_('about.title')}/>
    <Block inset>

      <p>
        {$_('about.email_feedback')}
      <a href='mailto:{feedbackEmail}'>{feedbackEmail}</a>
      </p>
      <p>
      <a href=#>{$_('about.share')}</a>
      </p>

      <center>
        {$_('about.version')} {version} <br/>
        Copyright &copy; Martin Jablecnik 2020
      </center>
    </Block>
  </Page>
</Popup>

<script>
  import {
    Page,
    Navbar, NavRight, Link,
    Block, Popup, Icon
  } from 'framework7-svelte';
  import Header  from '../components/Header.svelte';
  import { feedbackEmail, version, appName }  from '../js/config.js';
  import { _ } from 'svelte-i18n';
  
  export let name;
</script>
