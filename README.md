class.extend
============
copy/paste node package implementation of http://learn.javascript.ru/files/tutorial/js/class-extend.js
enables mixin and static members

Install
-------
    npm install class.extend2

Usage
-------
    var Class = require('class.extend2');

    var Person = Class.extend({
      init: function(isDancing){
        this.dancing = isDancing;
      },
      dance: function(){
        return this.dancing;
      }
    });

    var Ninja = Person.extend({
      init: function(){
        this._super( false );
      },
      dance: function(){
        // Call the inherited version of dance()
        return this._super();
      },
      swingSword: function(){
        return true;
      }
    });

    var p = new Person(true);

    var n = new Ninja();