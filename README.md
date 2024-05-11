

- Generar un API_KEY de Google Maps (el vídeo lo explica) y añadirla en el fichero *AndroidManifest.xml* 

```xml
 <meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="TU_API_KEY"/>
```

- Crear un API_KEY en OpenRouteService (explicado en el vídeo) y añadirla en el fichero *MainActivity*

```kotlin
private fun createRoute() {
    CoroutineScope(Dispatchers.IO).launch {
        val call = getRetrofit().create(ApiService::class.java)
            .getRoute("TU_API_KEY", start, end)
        if (call.isSuccessful) {
            drawRoute(call.body())
        } else {
            Log.i("aris", "KO")
        }
    }
}
```

## COLABORA.

Este proyecto es totalmente GRATUITO por lo que puedes aportar tu grano de arena de múltiples formas.

- Dale a FAV al proyecto (Star)
- Sígueme en mis [redes sociales](https://aristi.dev)
- Nomíname a [GITHUB STAR](https://stars.github.com/nominate/)
