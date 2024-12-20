# AI Prompt Examples

> Generate a slider meta box which let people create slides, each slide contain image, title, description, cta button. Here is the schema: https://raw.githubusercontent.com/wpmetabox/schema/refs/heads/main/schema.json

Output (VS Code \ Language: PHP):

```php
<?php
add_filter( 'rwmb_meta_boxes', 'your_prefix_register_meta_boxes' );

function your_prefix_register_meta_boxes( $meta_boxes ) {
    $meta_boxes[] = array(
        'title'      => __( 'Slider', 'your-text-domain' ),
        'id'         => 'slider',
        'post_types' => array( 'post', 'page' ),
        'fields'     => array(
            array(
                'id'          => 'slides',
                'type'        => 'group',
                'clone'       => true,
                'sort_clone'  => true,
                'fields'      => array(
                    array(
                        'name' => __( 'Image', 'your-text-domain' ),
                        'id'   => 'image',
                        'type' => 'image_advanced',
                    ),
                    array(
                        'name' => __( 'Title', 'your-text-domain' ),
                        'id'   => 'title',
                        'type' => 'text',
                    ),
                    array(
                        'name' => __( 'Description', 'your-text-domain' ),
                        'id'   => 'description',
                        'type' => 'textarea',
                    ),
                    array(
                        'name' => __( 'CTA Button', 'your-text-domain' ),
                        'id'   => 'cta_button',
                        'type' => 'text',
                    ),
                ),
            ),
        ),
    );

    return $meta_boxes;
}
?>
```

If you choose other languages, the code will be generated in that language.