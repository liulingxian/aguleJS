#  postcss
简介:我们在开发的过程中 避免不了写css兼容 为何不用机器来做呢?
##  基于gulp
```js
var gulp=require('gulp');
gulp.task('autoprefixer',function(){
	var postcss=require('gulp-postcss');//css 处理平台
	var autoprefixer=require('autoprefixer');//自动添加前缀

	gulp.src('./*.css')//链式调用   所有的css 同级目录下
	       .pipe(postcss([autoprefixer({browsers: ['last 2 versions']})]))//开始加前缀
	       .pipe(gulp.dest('./dist/postcss'))//输出到文件下
});
gulp.task('default',['autoprefixer'])
```