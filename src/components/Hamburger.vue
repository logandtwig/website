<template>
  <div class="menu btn14" data-menu="14">
    <div class="icon-circle"></div>
    <div class="icon"></div>
  </div>
</template>

<style lang="scss">
$dark: #212121;
$light: #efefef;
$color: #b3e5fc;

@mixin btn($left, $top) {
  position: relative;
  width: 60px;
  height: 60px;
  transition-duration: 0.5s;
}

@mixin icon($height, $width) {
  transition-duration: 0.5s;
  position: absolute;
  height: $height;
  width: $width;
  top: 27px;
  background-color: $dark;
  left: 14px;
}

@mixin icon-before($height, $width, $top) {
  transition-duration: 0.5s;
  position: absolute;
  width: $width;
  height: $height;
  background-color: $dark;
  content: "";
  top: $top;
}

@mixin icon-after($height, $width, $top) {
  transition-duration: 0.5s;
  position: absolute;
  width: $width;
  height: $height;
  background-color: $dark;
  content: "";
  top: $top;
}

@mixin icon-circle($height, $width) {
  transition-duration: 0.5s;
  position: absolute;
  height: $height;
  width: $width;
  border-radius: 100%;
  background: transparent;
  border: 4px solid black;
}

.btn14 {
  @include btn(15px, 50px);
  .icon-circle {
    @include icon-circle(50px, 50px);
    &:hover {
      background: #fff;
    }
  }

  .icon {
    @include icon(4px, 30px);
    border-radius: 4px;

    &:before {
      @include icon-before(4px, 30px, -10px);
      border-radius: 4px;
    }

    &:after {
      @include icon-after(4px, 30px, 10px);
      border-radius: 4px;
    }
  }

  &.open {
    .icon-circle {
      background: #fff;
    }
    .icon {
      transition-duration: 0.5s;
      background: transparent;

      &:before {
        transform: rotateZ(45deg) scaleX(1.25) translate(6.5px, 6.5px);
      }

      &:after {
        transform: rotateZ(-45deg) scaleX(1.25) translate(6px, -6px);
      }
    }
  }
  &:hover {
    cursor: pointer;
  }
}
</style>
