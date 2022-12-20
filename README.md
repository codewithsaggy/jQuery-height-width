# jQuery-height-width
jQuery height width get for sticky header issue



// element height/ width get and add in class
jQuery(document).ready(function( $ )
 { 
	
	var secH1 = jQuery(".padding_header").outerHeight();
	var secH2 = jQuery(".rightside-callaction").outerHeight();
	var additiontot = secH2 + secH1;
	console.log(additiontot);
	console.log(secH1);
	console.log(secH2);
$(".cstsection-2").css('top', additiontot + "px");
});



// Header sticky

	jQuery(window).scroll(function( $ ) { 
		if (jQuery(document).scrollTop() > 50) {
			jQuery('.main_header').addClass('stickey');
		}else{
			jQuery('.main_header').removeClass('stickey');			
		}
	});
  
////////////////////////////////////////////////////////////////////////
Adding div element in html page

jQuery(document).ready(function ( $ ) { 
jQuery('.lSPager').wrap('<div class="main-thumb"></div>');
});


/////////////////////////////////////////////////////////////////////////
HTML remove element from page.

jQuery(document).ready(function($){
    $('.gridlist-toggle').remove();
});

////////////////////////////////////////////////////////////////////////
*trigger custom second search button*

jQuery(document).ready(function(){
		jQuery('body').on('click', "#search-site-btns", function(){
		jQuery('body').find(".jet-search__submit").click();
	});

//////////////////////////////////////////////////////////////////////

*Dynamic URL search query add*

jQuery(document).ready(function(){

jQuery('body').on('click','#search-shop-btn', function() {
  	var searchString = '';
	var preurl ="https://shop.partwell.com/search?q=";
	var posturl = "&options%5Bprefix%5D=last";
  
	if(jQuery("body input.jet-search__field").val() != ''){
	var searchString = jQuery('body input.jet-search__field').val();
  	document.location.href = preurl + searchString + posturl;
	}
});
});

//////////////////////////////////////////////////////////////////////

SHORTCODES FOR ACF 

<?php
add_shortcode( 'COMPANY-DETAILS', 'home_box_filter_area_cb' );
function home_box_filter_area_cb(){
    $html = "";
    ob_start();
    ?>
***************************** html code here *****************************
    <?php
    $html .= ob_get_clean();
    return $html;
}


//////////////////////////////////////////////////////////////////////

ACF get fields value in html structure.

	global $post;
	$post_id = $post->ID;
	$address = get_field( 'address', $post_id );
	$phone = get_field( 'phone', $post_id );
	$email = get_field( 'email', $post_id );
	$websites = get_field( 'websites', $post_id );
    ?>
    <div class="container">
  <div class="row">
		<?php if( !empty( $address ) ){ ?>
		<div class="col-md-12">
			<p class="col-md-3">Address:</p>
			<p class="col-md-9"><?php echo $address; ?></p>
		</div>
		<?php } ?>
		<?php if( !empty( $phone ) ){ ?>
		<div class="col-md-12">
			<p class="col-md-3">Phone:</p>
			<a class="col-md-9" href="tel:<?php echo $phone; ?>"><?php echo $phone; ?></a>
		</div>
		<?php } ?>
		<?php if( !empty( $email ) ){ ?>
		<div class="col-md-12">
			<p class="col-md-3">Email:</p>
			<a class="col-md-9" href="mailto:<?php echo $email; ?>"><?php echo $email; ?></a>
		</div>
		<?php } ?>
		<?php if( !empty( $websites ) ){ ?>
		<div class="col-md-12">
			<p class="col-md-3">Website:</p>
			<a class="col-md-9" href="<?php echo esc_url( $websites ); ?>"><?php echo $websites; ?></a>
		</div>
		<?php } ?>
	</div>
</div>

//////////////////////////////////////////////////////////////////////
for tiny slider customize function to change bg on parent class. 

      var customizedFunction = function (info, eventName) {
        console.log( info );
        
        imageUrl = '/tips360/assets/images/banner.png';
        imageUrl2 = '/tips360/assets/images/banner2.png';
        imageUrl3 = '/tips360/assets/images/banner3.png';

        if( info.index == 1 ){
          $(".hero-area").css("background-image", "url(" + imageUrl + ")");
        }
        if( info.index == 2 ){
          $(".hero-area").css("background-image", "url(" + imageUrl2 + ")");
        }
        if( info.index == 3 ){
          $(".hero-area").css("background-image", "url(" + imageUrl3 + ")");
        }
      }
      
