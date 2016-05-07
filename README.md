
### 快速构建gulp环境    
=====================
　　1. 安装node环境   
　　2. npm install gulp -g   
　　3. npm init   
　　4. 创建项目工程文件     
　　5. 在项目文件地址执行 npm install gulp --save-dev  && npm install gulp-less --save-dev    
　　6. 在项目文件中新建**gulpfile.js**  
```javascript
            //导入工具包 require('node_modules里对应模块')
            var gulp = require('gulp'), //本地安装gulp所用到的地方
                less = require('gulp-less');
             
            //定义一个testLess任务（自定义任务名称）
            gulp.task('testLess', function () {
                gulp.src('src/less/index.less') //该任务针对的文件
                    .pipe(less()) //该任务调用的模块
                    .pipe(gulp.dest('src/css')); //将会在src/css下生成index.css
            });
             
            gulp.task('default',['testLess', 'elseTask']); //定义默认任务
             
            //gulp.task(name[, deps], fn) 定义任务  name：任务名称 deps：依赖任务名称 fn：回调函数
            //gulp.src(globs[, options]) 执行任务处理的文件  globs：处理的文件路径(字符串或者字符串数组) 
            //gulp.dest(path[, options]) 处理完后文件生成路径

``` 

　　7. gulp testLess

================
###重点

　　**gulpfile.js**是gulp的配置文件。也是核心。（我建议大家不要深究这玩意，毕竟这东西只是个自动化**工具**，会用就行。）
