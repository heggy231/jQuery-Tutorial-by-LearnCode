# jQuery-Tutorial-by-LearnCode
 * jQuery tutorial for serious beginners
    - this includes excercise files for jQuery Tutorial for Beginners video series

## Lesson 1:
  * Learned basic structure of jQuery
  * Created template jQuery
    ex: always start with $(function() {

    	});
  * Animate using .slideUp .hide .toggle
  * Insert curly when using .css({ })
  * Style any {} as js object enter
  * .css value put it inside ""
    ex: .css( { color: "red"})
  * Multiple .css key value separate it with comma (,)
  * camelCase any time .css property has dash (-) or " "
    ex: $("#panel1").css({
    	  fontWeight: 'bold',
    	  "font-weight": 'normal'
    	});

## Lesson 2: 
  * Eventlistener 'click' in js
  	ex) $(#btn1).on('click', function() {
  			// do something when click happens
  			$(#panel1).fadeIn(200);
  		});
  * using .html to change text on the page
  * .slideToggle(200); animation when 'click' event -> triggers callback
  * .fadeIn(200) .fadeOut(200) use number always in parenthesis
  * .find('.panel-body') to search through html doc
  * 'hover' effect  .on('hover', function() { * do something * }); 
  *  chain methods
     ex) $("#panel1").slideUp(1000).delay(1000).slideDown(1000);

## Lesson 3:
  * Refactor to eliminate repeating codes 
  * Usage of css class to select multiple elements
    note: .panel-button is class here
    ex) $('.panel-button').on('click', function() {
          // 'data-panelid' is custom attribute
          var panelId = $(this).attr('data-panelid');
          // inserts var content inside of selected panel body
          $('#'+panelId+' .panel-body').html(content);
        });
  * See which panel was clicked on using
    ex) var panelId = $(this).attr('id') 
        alert(panelClass);
    note: this points to left of dot rule
        - note: '.panel-button' was clicked and triggers id to show

## Lesson 4:
  * DOM transversal with jQuery (cutting down the complication)
  * jQuery is really made for DOM transversal
  * In console: $('li') shows all li
      $('li').first()
      $('li').last() // last one on the entire page; not last on list
      $('li').first().hide() // hide first li
      $('li').first().show()
      $('li').eq(0) // get the first index; first one
      $('li').eq(1) // get the 2nd index; 2nd one
      $('ul:first').children() // get first child 
      $('ul:first').children().hide()
      $('li:first').siblings() // all direct siblings not including itself
      $('li:first').parent() // ul that is parent of li
      $('li').eq(4) // 1 in this ex
      $('li').eq(4).parent() // ul.sublist 
      $('li').eq(4).parent().parent().parent() // chaining upto ul.list
      $('li').eq(4).parent().parent().prev() // 3 .prev() immediate sibling 
      $('li').eq(4).parent().parent().prev().prev() // 2 prev of prev sibling
      $('li').eq(4).parent().parent().prev().prev().next() // back to 3, next sibling
      $('li').first().next() // 2, same as $('li').eq(4).parent().parent().prev().prev()
      $('li').eq(1) // 2
  * Usecase for using transversal DOM
    - $(this).next().hide(); <= .on('click') of li next li get hidden
    - $(this).next().remove(); <= work if you want to keep deleting
  * event listener for li include nested li and its parent li.  assign class for nested li group to have special function.  
    ex) if($(this).parent().is('.sublist')) {
          $(this).hide(); /* 'this' >> li */
        }

  * .filter('.special') to filer only .special class and chain to .remove()
  * .find('li').addClass('.special') to element
    result: Before <li>
            After  <li class="special> 
  * .closest('.list') looks for its closest class .list
  * $(this).siblings().addClass('special') > result: all my siblings gets special class except me.
  * .next().hide() vs .next().remove()
    hides next element from viewing currently clicked on vs.
    removes next element
  * .find('li').filter(':first').addClass('special') filters first li