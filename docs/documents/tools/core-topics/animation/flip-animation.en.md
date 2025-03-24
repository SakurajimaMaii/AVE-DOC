# Flip Animation

## Flip animation with Y axis

[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

=== "kotlin"

    ```kotlin
    getBinding().textview1.setOnLongClickListener {
        flipYAnimation(getBinding().textview1, getBinding().textview2)
        false
    }
    getBinding().textview2.setOnLongClickListener {
        flipYAnimation(getBinding().textview1, getBinding().textview2)
        false
    }
    ```

=== "java"

    ```java
    getBinding().textview1.setOnLongClickListener(v -> {
        RotationKt.flipYAnimation(getBinding().textview1, getBinding().textview2);
        return false;
    });

    getBinding().textview2.setOnLongClickListener(v -> {
        RotationKt.flipYAnimation(getBinding().textview1, getBinding().textview2);
        return false;
    });
    ```

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/flip_y_animation.mp4" type="video/mp4">
    </video>
</center>

## Flip animation with X axis

[:octicons-tag-24: Version 0.5.3](https://sakurajimamaii.github.io/AVE-DOC/version/tools/#053)

=== "kotlin"

    ```kotlin
    getBinding().textview1.setOnLongClickListener {
        flipXAnimation(getBinding().textview1, getBinding().textview2)
        false
    }
    getBinding().textview2.setOnLongClickListener {
        flipXAnimation(getBinding().textview1, getBinding().textview2)
        false
    }
    ```

=== "java"

    ```java
    getBinding().textview1.setOnLongClickListener(v -> {
        RotationKt.flipXAnimation(getBinding().textview1, getBinding().textview2);
        return false;
    });

    getBinding().textview2.setOnLongClickListener(v -> {
        RotationKt.flipXAnimation(getBinding().textview1, getBinding().textview2);
        return false;
    });
    ```

<center>
    <video width="250" controls="controls" autoplay="autoplay">
        <source src="../img/flip_x_animation.mp4" type="video/mp4">
    </video>
</center>

## Sample code

[Sample code](https://github.com/SakurajimaMaii/Android-Vast-Extension/blob/develop/app/src/main/kotlin/com/ave/vastgui/app/activity/anim/FlipAnimActivity.kt){ .md-button }
