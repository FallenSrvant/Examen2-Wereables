1. Se hace uso de Flaticon para el diseño de los iconos de la aplicación
   https://www.flaticon.es
   en App/manifests/AndroidManifest.xml
   <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_chat" 
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_chat_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.ChatAppKotlin"
        tools:targetApi="31">
2. Se hace uso de lottie para el diseño de animación de bienvenida
   https://lottiefiles.com/es/
   se agrega build.gradle a nivel Module en el apartado de dependencies
   dependencies{
   implementation (libs.lottie)
   }
   Nota: la animación que vayamos a descargar se guarda en formato.json y se guarda creando una carpeta llamada assets en
   AndroidStudioProjects\ChatAppKotlin\app\src\main
   
4. Se hace uso de una actividad de SplashScreen para la pantalla de bienvenida.
   a) en SplashScreen.xml se hace uso de la vista
   <com.airbnb.lottie.LottieAnimationView
            android:layout_width="300dp"
            android:layout_height="300dp"
            app:lottie_fileName="chat_animacion.json"
            app:lottie_imageAssetsFolder="assets"
            app:lottie_loop="true"
            app:lottie_autoPlay="true"/>
   b) en SplashScreen.kt se agrega la función de MostrarBienvenida para añadir la funcionalidad de la imagen con animación

5. El resto del codigo es lo convencional al crear actividades una para la pantalla de inicio, una para la de registro y otra para el login.
6. El sistema usa el sistema de firebase como:
    implementation("com.google.firebase:firebase-auth:23.1.0")
    implementation("com.google.firebase:firebase-database:21.0.0")
   que son las implementación para el sistema de autenticación y la base de datos.
7. La aplicación permite:
     1. Crear un usuario
     2. Iniciar sesión
     3. Cerrar sesión
     4. Incluye validación de entradas en el input.
