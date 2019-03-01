# picasso
picasso is a free lightweight wordpress theme for designers and artists

## Custom post types:
### notes
For short notes and announcments. Using the title and the content in one colum

### stories
For longer stories with images. Tow column display using the attached images with optional descriptions

### projects
Full project documentation with Title, Categories and Metadata. Large featurette layout for the attached images

## Custom page templates:
### one-column-plain

### one-colum-header

### one-colum-gallery

### one-colum-slider

# Research
Adding custom post types in the functions.php
``` php
function codex_custom_init() {
    $args = array(
      'public' => true,
      'label'  => 'Books'
    );
    register_post_type( 'book', $args );
}
add_action( 'init', 'codex_custom_init' );
```

Displaying a custom post type in the loop
``` php
$args = array( 'post_type' => 'product', 'posts_per_page' => 10 );
$loop = new WP_Query( $args );
while ( $loop->have_posts() ) : $loop->the_post();
  the_title();
  echo '<div class="entry-content">';
  the_content();
  echo '</div>';
endwhile;
```
