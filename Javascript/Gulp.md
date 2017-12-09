# Gulp

## gulpfile

```
var
  gulp       = require('gulp'),
  less       = require('gulp-less'),           // Compile LESS to CSS
  sourcemaps = require('gulp-sourcemaps'),     // Generate SourceMaps
  plumber    = require('gulp-plumber'),
  uglifycss  = require('gulp-uglifycss'),
  concat     = require('gulp-concat'),
  minify     = require('gulp-minify'),
  imagemin   = require('gulp-imagemin');

 
// ==================   LESS TASK  ================
gulp.task('less', function()
{
  return gulp.src(['./src/main/drupal/sites/all/themes/manPower/less/style.less', 
	'./src/main/drupal/sites/all/themes/manPower/less/mon-manpower.less',
        './src/main/drupal/sites/all/themes/manPower/less/mde.less'
    ])  // use style.less as input
    .pipe(sourcemaps.init())                                               // Create sourcemaps
    .pipe(plumber({
	errorHandler: function (err) {
	    console.log(err);
	    this.emit('end');
	}
    }))
    .pipe(less())                                                          // Compile less to css
    .pipe(sourcemaps.write('../maps'))                                     // Write the map file to ../maps
    .pipe(gulp.dest('./src/main/drupal/sites/all/themes/manPower/css/'));         // Compile to less-css directory
});

gulp.task('lessprod', function()
{
  return gulp.src(['./src/main/drupal/sites/all/themes/manPower/less/style.less', 
	'./src/main/drupal/sites/all/themes/manPower/less/mon-manpower.less',
        './src/main/drupal/sites/all/themes/manPower/less/mde.less'
    ])  // use style.less as input
    .pipe(less())                                                          // Compile less to css
    .pipe(gulp.dest('./src/main/drupal/sites/all/themes/manPower/css/'));         // Compile to less-css directory
});


// ====================	MINIFY CSS FILES TASK ======================
gulp.task('css', function () {
  gulp.src(['./src/main/drupal/sites/all/themes/manPower/css/mon-manpower.css',
	'./src/main/drupal/sites/all/themes/manPower/css/mde.css', 
	'./src/main/drupal/sites/all/themes/manPower/css/style.css'])
    .pipe(uglifycss({
    //  "maxLineLen": 80,
      "uglyComments": false
    }))
    .pipe(gulp.dest('./src/main/drupal/sites/all/themes/manPower/css/'));
});

// ====================	CONCAT JS FILES TASK ======================
gulp.task('concat', function() {
  return gulp.src([
	'./src/main/drupal/sites/all/themes/manPower/vendor/jquery-ui-autocomplete.min.js',
	'./src/main/drupal/sites/all/themes/manPower/vendor/bootstrap/js/bootstrap.min',
	'./src/main/drupal/sites/all/themes/manPower/vendor/jasny-bootstrap/jasny-bootstrap.min.js',
	'./src/main/drupal/sites/all/themes/manPower/js/custom.js',
    ])
    .pipe(concat('homepage.js'))
    .pipe(gulp.dest('./src/main/drupal/sites/all/themes/manPower/js/'));
});

// ====================	MINIFY JS FILES TASK ======================
gulp.task('compress', function() {
  gulp.src([
	'./src/main/drupal/sites/all/themes/manPower/js/homepage.js'
    ])
    .pipe(minify(
/*{
        ext:{
            src:'-debug.js',
            min:'.js'
        },*/
      //  exclude: ['tasks'],
      //  ignoreFiles: ['.combo.js', '-min.js']
    ))
    .pipe(gulp.dest('./src/main/drupal/sites/all/themes/manPower/js/'))
});

// ====================	IMAGE MINIFY TASK ======================
gulp.task('imagemin', function() {
    gulp.src([
	'./src/main/drupal/sites/all/themes/manPower/image/**/*',
    ])
    .pipe(imagemin())
    .pipe(gulp.dest('./src/main/drupal/sites/all/themes/manPower/image_o'))
});



// ====================	WATCH TASK ======================
gulp.task('watch', function()
{
     gulp.watch(['./src/main/drupal/sites/all/themes/manPower/**/**/*.less'], ['less']);
});


// ==================== DEFAULT TASK ===========================
gulp.task('default', ['watch', 'less', 'css']);
gulp.task('image', ['imagemin']);
//gulp.task('prod', ['css', 'less', 'concat', 'compress']);
gulp.task('prod', ['lessprod', 'css']);
```
