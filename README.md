# Estudios-rafael
🎤 ESTUDIOS RAFAEL

Aplicación profesional de canto y grabación musical.

Bienvenido a Estudios Rafael.

Funciones principales

- 🎙️ Grabación de voz en tiempo real.
- 🎵 Efectos profesionales para la voz.
- 🎧 Subir tus propias pistas musicales.
- 🎚️ Motor de audio profesional.
- 🎼 Cantar sobre pistas instrumentales.
- 📥 Descargar tus grabaciones en formato MP3.

Objetivo

Ofrecer un estudio musical desde tu teléfono Android.

Desarrollado para Estudios Rafael.

pluginManagement {
    repositories {
        google()
        mavenCentral()
        gradlePluginPortal()
    }
}

dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
    }
}

rootProject.name = "EstudiosRafael"
include ':app'
pluginManagement {
    repositories {
        google()
        mavenCentral()
        gradlePluginPortal()
    }
}

dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
    }
}

rootProject.name = "EstudiosRafael"
include ':app'

plugins {
    id 'com.android.application' version '8.6.1' apply false
}
plugins {
    id 'com.android.application' version '8.6.1' apply false


plugins {
    id 'com.android.application'
}

android {
    namespace 'com.estudiosrafael'
    compileSdk 35

    defaultConfig {
        applicationId 'com.estudiosrafael'
        minSdk 23
        targetSdk 35
        versionCode 1
        versionName '1.0'
    }
}

}