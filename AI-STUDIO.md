# Lawnchair 12.1 (legacy) — workspace para Google AI Studio

- Origen: `LawnchairLauncher/lawnchair`, rama `12.1-dev` @ `78873fa` (2023-11-10).
- Solo esta rama: el repo original trae también la 16 y otras ramas; aquí solo va la 12.1 legacy.
- `platform_frameworks_libs_systemui/` está **vendoreado** (copiado, no submódulo)
  en el commit `1827de1`, que es el que fija la rama 12.1-dev. `settings.gradle`
  lo necesita (`iconloaderlib`, `searchuilib`).
- `prebuilts/libs/` se conserva: el build lo necesita
  (`framework-11/12/12l.jar`, `SystemUI-statsd.jar`, `WindowManager-Shell.jar`).
- Excluido: `.idea/`, `build/`, `.gradle/`, `local.properties`.

## Notas para el agente de AI Studio
- El agente NO compila para entregar: compilar es trabajo local.
- `build.gradle` (raíz) ejecuta `git rev-parse --short=7 HEAD` al configurar;
  el árbol debe estar dentro de un repo git con al menos un commit.
- Nunca commitear keystores (`.jks`, `.keystore`), `local.properties`
  ni contraseñas: ver `.gitignore`.
