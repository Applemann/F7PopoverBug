<Page name="CategoryList">
  <Header />

  <Block strong inset>
    <BlockTitle medium>{$_('category.title')}</BlockTitle>
    <List>
      {#each categoryData as category, id}
        <ListItem text="" link="#">
          <h3>{category}</h3>
        </ListItem>
      {/each}
    </List>
  </Block>
</Page>

<script>
  import { 
    Page, Link,
    Block, BlockTitle, 
    List, ListItem
  } from 'framework7-svelte';
  import Header from '../components/Header.svelte';
  import { _ } from 'svelte-i18n';
  let categoryData = ["test1", "test2", "test3", "test4"];
                   
</script>

<style>
</style>
