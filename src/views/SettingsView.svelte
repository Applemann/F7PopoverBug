<Page name="Settings">
  <Navbar backLink title={$_('settings.title')}>
  </Navbar>

  <Block>
    <List>
      <ListItem>
        <div>{$_('settings.words_limit')}</div>
        <Stepper small round fill value={30} min={10} max={100} step={10}
            on:stepperMinusClick={() => { if(wordsLimit > 10) { wordsLimit -= 10 } }}
            on:stepperPlusClick={() => { if(wordsLimit < 100) { wordsLimit += 10 } }} 
        ></Stepper>
      </ListItem>
      <ListItem>
        <div>
          {$_('settings.auto_sound')}
        </div>
          <Toggle checked color="blue"></Toggle>
      </ListItem>
      <ListItem>
        <div>
          {$_('settings.night_theme')}
        </div>
          <Toggle checked color="blue"></Toggle>
      </ListItem>
    </List>
  </Block>
</Page>

<script>
  import { 
    Page, Link, Navbar,
    Block, BlockTitle, 
    List, ListItem,
    Toggle, Stepper
  } from 'framework7-svelte';
  import Header from '../components/Header.svelte';
  import { _ } from 'svelte-i18n';

</script>

<style>
</style>

