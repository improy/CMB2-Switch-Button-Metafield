# CMB2-Switch-Button-Metafield
### Switch-button metafield for CMB2. 

* The code below is use to integrate switch-button directly in to the theme

## How to integrate switch metafield in your theme
1. Create or download the file and make sure the path is correct
2. add the following codes in you CMB2 main file

/** START --- Initialize the CMB2 Metabox & Related Classes */
function initialize_showcase_meta_box() {
		require_once('switch_metafield.php');			
}add_action('init', 'initialize_showcase_meta_box', 9999 );

/** LOAD --- Related CSS and JS */
function load_custom_cmb2_script() {
	wp_enqueue_style( 'cmb2_switch-css', 'switch_metafield.css', false, '1.0.0' );
	wp_enqueue_script( 'cmb2_switch-js', 'switch_metafield.js' , '', '1.0.0', true );
} add_action( 'admin_enqueue_scripts', 'load_custom_cmb2_script', 20 );

## How to use switch metafield
$cmb->add_field( array(
	'name'    => __( 'Field Name', 'cmb2' ),
	'desc'    => __( 'Field Description', 'cmb2' ),
	'id'      => 'your_switch_button',
	'type'    => 'switch',
	'default'    => 0,
	'label'    => array('on'=> 'Yes', 'off'=> 'No')
));
