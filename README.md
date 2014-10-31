Term taxonomy meta
==================

Term taxonomy meta for WordPress, so it allows extra information to be added to terms.

### Usage

You can extend class for term meta called `TP_Term_Meta`.

### Example

```
/**
 * Responsible employee
 *
 * @package    Your_Theme
 * @subpackage Term_Taxonomy_Meta
 */
class Responsible_Employee extends TP_Term_Meta {
	function display( $term ) {
		?>

		<tr class="form-field">

			<th scope="row" valign="top">
				<label for="employee"><?php _e( 'Responsible employee', 'tp' ); ?></label>
			</th>

			<td>
				<input type="text" name="employee" id="employee" value="<?php echo get_term_meta( $term->term_taxonomy_id, 'employee', true ); ?>" />
			</td>

		</tr>

		<?php
	}

	function save( $term_id, $tt_id ) {
		update_term_meta( $tt_id, 'employee', $_POST['employee'] );
	}
}
new Responsible_Employee( 'branche' );
```

### API

The API works exactly the same as WordPress' meta API.

```
add_term_meta( $object_id, $meta_key, $meta_value, $unique = false )
```

See [`add_metadata`](http://codex.wordpress.org/Function_Reference/add_metadata).

```
update_term_meta( $object_id, $meta_key, $meta_value, $unique = false )
```

See [`update_metadata`](http://codex.wordpress.org/Function_Reference/update_metadata).

```
get_term_meta( $object_id, $meta_key, $meta_value, $unique = false )
```

See [`get_metadata`](http://codex.wordpress.org/Function_Reference/get_metadata).

```
delete_term_meta( $object_id, $meta_key, $meta_value, $unique = false )
```

See [`delete_metadata`](http://codex.wordpress.org/Function_Reference/delete_metadata).
