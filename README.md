[Recline view][] providing graphing capabilities using [Flotr2][] graphing library.

As a Recline view it is also a standard Backbone view.

[Recline view]: http://reclinejs.com/docs/views.html
[Flotr2]: http://www.humblesoftware.com/flotr2/

## Usage

Create a view and render it:

    var dataset = new recline.Model.Dataset({
      records: [ ['A','B','C'], [1,2,3] ]
    });
    var view = new recline.View.Flotr2({
      model: data
    });
    // NB: do *not* provide an el argument to the view but let the view
    // generate the element itself (you can then append view.el to the DOM)
    // e.g.
    $('.fixtures').append(view.el);
    // now render the view
    view.render();

As standard for Recline views you can pass an optional state parameter in the initialization hash. It should have the following structure:

    { 
      group: {column name for x-axis},
      series: [{column name for series A}, {column name series B}, ... ],
      graphType: 'line',
      // custom Flotr2 options - see http://www.humblesoftware.com/flotr2/documentation#configuration
      graphOptions: { ... }
    }

