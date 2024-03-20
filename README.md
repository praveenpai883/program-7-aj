<!DOCTYPE html>
<html ng-app="userApp">
<head>
<title>AngularJS CRUD Application for Users</title>
</head>
<body ng-controller="UserController">
<script type="text/javascript" src="//ajax.googleapis.com/ajax/libs/angularjs/1.8.2/a 
 ngular.min.js"> </script>
<h1>User Management</h1>
<table border="1">
<thead>
<tr>
<th>Name</th>
<th>Email</th>
<th>Actions</th>
</tr>
</thead>
<tbody>
<tr ng-repeat="user in users">
<td>{{ user.name }}</td>
<td>{{ user.email }}</td>
<td>
 <button ng-click="editUser(user)">Edit</button>
 <button ng-click="deleteUser(user)">Delete</button>
</td>
</tr>
</tbody>
</table>
<hr>
<h2>Create User</h2>
<input type="text" ng-model="newUser.name" placeholder="Name">
<input type="email" ng-model="newUser.email" placeholder="Email">
<button ng-click="createUser()">Create</button>
<hr>
<h2>Edit User</h2>
<input type="text" ng-model="editedUser.name" placeholder="Name">
<input type="email" ng-model="editedUser.email" placeholder="Email">
<button ng-click="updateUser()">Update</button>
<script src="Program7.js"></script>
</body>
</html>
Program7.js
angular.module('userApp', []) .controller('UserController', function($scope) {
$scope.users = [
{ name: 'abcd', email: 'abcd@gmail.com' },
{ name: 'trainee', email: 'trainee@yahoo.com' }
];
$scope.newUser = {};
$scope.createUser = function() {
$scope.users.push($scope.newUser);
$scope.newUser = {};
};
$scope.editUser = function(user) {
$scope.editedUser = user;
};
$scope.updateUser = function() {
$scope.editedUser = {};
};
$scope.deleteUser = function(user) {
$scope.users.splice($scope.users.indexOf(user), 1);
};
});
