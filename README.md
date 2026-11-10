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
package com.estudiosrafael;

import android.app.Activity;
import android.os.Bundle;
import android.graphics.Color;
import android.view.Gravity;
import android.widget.*;
import android.media.MediaRecorder;
import android.Manifest;
import android.content.pm.PackageManager;
import android.os.Build;
import java.io.File;

public class MainActivity extends Activity {

    MediaRecorder recorder;
    File recording;

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        LinearLayout layout = new LinearLayout(this);
        layout.setOrientation(LinearLayout.VERTICAL);
        layout.setGravity(Gravity.CENTER);
        layout.setPadding(25, 30, 25, 30);
        layout.setBackgroundColor(Color.rgb(18,18,35));

        TextView title = new TextView(this);
        title.setText("🎤 ESTUDIOS RAFAEL");
        title.setTextSize(30);
        title.setTextColor(Color.WHITE);
        title.setGravity(Gravity.CENTER);
        layout.addView(title);

        TextView subtitle = new TextView(this);
        subtitle.setText("Tu estudio musical profesional");
        subtitle.setTextColor(Color.LTGRAY);
        subtitle.setTextSize(17);
        layout.addView(subtitle);

        addButton(layout, "🎙️ GRABAR VOZ", v -> startRecording());
        addButton(layout, "⏹ DETENER GRABACIÓN", v -> stopRecording());
        addButton(layout, "🎵 SUBIR MI PISTA", v ->
            Toast.makeText(this, "Próximamente", Toast.LENGTH_SHORT).show());
        addButton(layout, "🎧 EFECTOS DE VOZ", v ->
            Toast.makeText(this, "Próximamente", Toast.LENGTH_SHORT).show());
        addButton(layout, "📥 DESCARGAR MP3", v ->
            Toast.makeText(this, "Conversión MP3 pendiente", Toast.LENGTH_SHORT).show());

        setContentView(layout);
    }

    void addButton(LinearLayout layout, String name,
                   android.view.View.OnClickListener action) {
        Button button = new Button(this);
        button.setText(name);
        layout.addView(button);
        button.setOnClickListener(action);
    }

    void startRecording() {
        if (checkSelfPermission(Manifest.permission.RECORD_AUDIO)
                != PackageManager.PERMISSION_GRANTED) {
            requestPermissions(
                new String[]{Manifest.permission.RECORD_AUDIO}, 10);
            return;
        }

        try {
            File folder = getExternalFilesDir("Music");
            recording = new File(folder, "Grabacion.m4a");

            if (Build.VERSION.SDK_INT >= 31) {
                recorder = new MediaRecorder(this);
            } else {
                recorder = new MediaRecorder();
            }

            recorder.setAudioSource(MediaRecorder.AudioSource.MIC);
            recorder.setOutputFormat(MediaRecorder.OutputFormat.MPEG_4);
            recorder.setAudioEncoder(MediaRecorder.AudioEncoder.AAC);
            recorder.setOutputFile(recording.getAbsolutePath());
            recorder.prepare();
            recorder.start();

            Toast.makeText(this, "Grabando voz...", Toast.LENGTH_SHORT).show();

        } catch (Exception e) {
            Toast.makeText(this, "Error al grabar", Toast.LENGTH_SHORT).show();
        }
    }

    void stopRecording() {
        if (recorder != null) {
            try {
                recorder.stop();
                recorder.release();
                recorder = null;
                Toast.makeText(this, "Grabación guardada", Toast.LENGTH_LONG).show();
            } catch (Exception e) {
                Toast.makeText(this, "Error al guardar", Toast.LENGTH_SHORT).show();
            }
        }
    }
}
package com.estudiosrafael;

import android.app.Activity;
import android.os.Bundle;
import android.graphics.Color;
import android.widget.TextView;
import android.widget.LinearLayout;

public class MainActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        LinearLayout layout = new LinearLayout(this);
        layout.setOrientation(LinearLayout.VERTICAL);
        layout.setGravity(17);
        layout.setBackgroundColor(Color.WHITE);

        TextView titulo = new TextView(this);
        titulo.setText("Bienvenido a Estudios Rafael");
        titulo.setTextSize(26);
        titulo.setTextColor(Color.BLACK);

        layout.addView(titulo);
        setContentView(layout);
    }
}package com.estudiosrafael;

import android.app.Activity;
import android.os.Bundle;
import android.graphics.Color;
import android.widget.TextView;
import android.widget.LinearLayout;

public class MainActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        LinearLayout layout = new LinearLayout(this);
        layout.setOrientation(LinearLayout.VERTICAL);
        layout.setGravity(17);
        layout.setBackgroundColor(Color.WHITE);

        TextView titulo = new TextView(this);
        titulo.setText("Bienvenido a Estudios Rafael");
        titulo.setTextSize(26);
        titulo.setTextColor(Color.BLACK);

        layout.addView(titulo);
        setContentView(layout);
    }
} package com.estudiosrafael;

import android.app.Activity;
import android.os.Bundle;
import android.graphics.Color;
import android.widget.TextView;
import android.widget.LinearLayout;

public class MainActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        LinearLayout layout = new LinearLayout(this);
        layout.setOrientation(LinearLayout.VERTICAL);
        layout.setGravity(17);
        layout.setBackgroundColor(Color.WHITE);

        TextView titulo = new TextView(this);
        titulo.setText("Bienvenido a Estudios Rafael");
        titulo.setTextSize(26);
        titulo.setTextColor(Color.BLACK);

        layout.addView(titulo);
        setContentView(layout);
    }
} package com.estudiosrafael;

import android.app.Activity;
import android.os.Bundle;
import android.graphics.Color;
import android.widget.TextView;
import android.widget.LinearLayout;

public class MainActivity extends Activity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        LinearLayout layout = new LinearLayout(this);
        layout.setOrientation(LinearLayout.VERTICAL);
        layout.setGravity(17);
        layout.setBackgroundColor(Color.WHITE);

        TextView titulo = new TextView(this);
        titulo.setText("Bienvenido a Estudios Rafael");
        titulo.setTextSize(26);
        titulo.setTextColor(Color.BLACK);

        layout.addView(titulo);
        setContentView(layout);
    }
}