---
layout: post
title:  "Solving a Toggle"
date:   2017-06-09 08:19: -0400
categories: jekyll update
---
The definition of toggle is a key or command that changes between two different modes, such as the caps lock key.

One of the problems i had this week was to define a simple toggle in Angular.Js. i was thinking the exact same thing that you were "Well that sounds freaking easy"..yeah it does. Until you start passing the wrong argument through the function that looks 100% right and sit there for an hour smashing your face on the keyboard. The best way i can explain this, is by showing you 2 different codes.

Wrong:
{% highlight css %}
	function mainController ($scope){

	 $scope.services = [{service:'Web Dev- $', price:300, state:true} ,{service:'Design- $', price:200, state:true} , {service:'Integration- $', price:750 , state:true} , {service:'Training- $', price:562, state:true}];
	 $scope.sum = 0;
	 // $scope.state = false;

	$scope.total = function(price,state) {
		if (state === true){
		 $scope.sum += price;
	  }else {
	  	$scope.sum -= price;
	}
	};

	$scope.toggle = function(state){
		console.log('state before: ', state);
		state = !state;
		console.log('state after:', state);
  }

}

{%endhighlight%}

Correct:
{% highlight css %}
	function mainController ($scope){

	 $scope.services = [{service:'Web Dev- $', price:300, state:true} ,{service:'Design- $', price:200, state:true} , {service:'Integration- $', price:750 , state:true} , {service:'Training- $', price:562, state:true}];
	 $scope.sum = 0;
	 // $scope.state = false;

	$scope.total = function(price,state) {
		if (state === true){
		 $scope.sum += price;
	  }else {
	  	$scope.sum -= price;
	}
	};

	$scope.toggle = function(service){
		console.log('state before: ', service.state);
		service.state = !service.state;
		console.log('service.state after:', service.state);
  }

}
{% endhighlight %}

Do they both look similar? Thats because they pretty much are the exact same except for one word. "Service", service the main name of the Object that have defined in my scope. "State" is a property of that object that i also have defined. Since i was call to toggle the state in the first one, it would toggle between true and false but it didn't know what object it was toggling. So after staring at for about 30 minutes my T.A. walked up and said why don't you just look for the object and the property of that object...... and of course he was right. One of the biggest problems that i have had learning how to code and program is being able to take a step back from a problem and attack it from a different angle. I hope that this helps you all understand and keep track of my progress in this bootcamp and time in my life.


Thank you,
	Cha'Sed Miller 

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
