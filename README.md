# d8-update-hooks
A list of common update hook snippets for D8

# Load all taxonomy terms in a vocabulary
```
$taxonomy_storage = \Drupal::service('entity_type.manager')->getStorage('taxonomy_term');
$terms = $taxonomy_storage->loadTree('your_taxonomy_bundle', 0, NULL, TRUE);
```
# Load all nodes of a given content type
```
$query = \Drupal::entityQuery('node')
  ->condition('type', 'bundle_name')
  ->execute();

$node_storage = \Drupal::service('entity_type.manager')->getStorage('node');
foreach ($query as $nid) {
  $node = $node_storage->load($nid);
}
```
