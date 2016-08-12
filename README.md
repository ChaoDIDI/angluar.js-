# angluar.js-

1. ng-app ng-model是angular.js中的指令

``` app指定一个范围的html代码是angular.js的作用域
    ng-model在当前作用域中定义一个属性,在作用域内可以访问
    ng-init初始化作用域内的属性的值
    ng-options 填充elect中的选择项,选择的结果就会是Object
```

 -  $scope 表示当前控制器的上下文,每一个controller中$scope是独立的

3. 在使用angluar.js时 需要几个项目依赖
```javascript
 <script src="assets/libs/angular.min.js"></script>
 <script src="assets/libs/angular-route.min.js"></script>
 <script src="assets/libs/angular-animate.js"></script>
```

1. 配置客户端地址
```javascript 
angular.module('app',['ngRoute','ngAnimate'])
//在config中使用provider的时候 需要加上Provider关键字后缀


//配置客户端路由地址 index.html#/  ..进行访问
angular.module('app').config(['$routeProvider',function ($routeProvider) {
    $routeProvider
        .when('/',{
            //路由的作用就是
            //把template和controller进行关联
            templateUrl:'./assets/tpl/index.html',
            controller:'indexCtrl'// 控制器名称
        })
        .when('/show/:id',{
            templateUrl:'./assets/tpl/show.html',
            controller:'showCtrl'
        })
        .when('/add',{
            templateUrl:'./assets/tpl/editor.html',
            controller:'editorCtrl'
        })
        .when('/editor/:id',{
            templateUrl:'./assets/tpl/editor.html',
            controller:'editorCtrl'
        })
}])
//在angular.js ngRoute 是引入依赖的时候命名的方式
//上面代码是angular.module  ('xxx' 跟页面ng-app='xxx'需要对应      ['ngRoute是引入依赖时的命名ngXxxx'])

//config 使用的时候需要加上后缀$routeProvider
```
