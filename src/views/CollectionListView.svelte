<Page name="CollectionList">
  <Header />
  <Block strong inset>
    <BlockTitle medium>First page</BlockTitle>
      <Button fill medium href="/CategoryList"> go to second page </Button>
  </Block>
</Page>

<script>
  import { 
    f7, f7ready, Page, 
    AccordionContent, 
    Navbar, Button,
    List, ListItem,
    BlockTitle, Block, 
  } from 'framework7-svelte';

  import Header from '../components/Header.svelte';
  import { _ } from 'svelte-i18n';

</script>

<style>
</style>
