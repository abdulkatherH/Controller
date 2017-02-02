(function(){
  'use strict';
  angular
    .module('app', ['ngRoute', 'ngCookies'])
    .config(config)
    .run(run);
  config.$inject = ['$rootProvider', '$locationProvider'];
  function config($rootProvider, $locationProvider){
    $rootProvider
      .when('/Login', {
        controller: 'LoginController',
        templateUrl: 'Login/Login.html',
        controllerAs: 'vm'
      })
      .when('/Register', {
        controller: 'RegisterController',
        templateUrl: 'Register/Register.html',
        controllerAs: 'vm'
      }
      .otherwise({ redirectTo: '/Login' });
  }
})();
