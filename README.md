# angularjs1-5-route-reload
AngularJS 1.5 Route Reload

Based on 'Route Reload' at https://www.youtube.com/watch?v=vOivhAKBVUU&list=PL6n9fhu94yhWKHkcL7RJmmXyxkuFB3KSl&index=36

#Route Reload

Use the ```reload``` method of the ```$route``` service object to avoid having to reload the entire page.
It will reload just the current route (e.g. '/students') of the application.

```javascript
[...]
.controller("studentsCtrl", function($http, $route) {
        var vm = this;
        
        vm.reloadData = function() {
            $route.reload();
        }
        
        // $http.get("StudentsService/GetAllStudents")
        //      .then(function(response) {
        //            vm.students = response.data;
        //       }, function(reason) {
        //            vm.error = reason.data;
        //       });
        vm.students = [{ id: 1, name: "Ben", gender: "Male", city: "London" }, { id: 2, name: "Matt", gender: "Male", city: "New York" }, { id: 3, name: "Pam", gender: "Female", city: "Chennai" }];
```

Then use it in the view as follows

```javascript
[...]
    <button data-ng-click="ctrl.reloadData()">Reload Data</button>
```

See script.js, index.html and styles.css how to implement this
