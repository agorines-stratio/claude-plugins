---
name: github-search
description: Busca código en repositorios de GitHub — soporta filtros por repo u organización Stratio.
argument-hint: "<query> [repo:owner/name] [org:name] [lang:yaml]"
user-invocable: true
allowed-tools: mcp__plugin_github-search_github__search_code, mcp__plugin_github-search_github__get_file_contents, mcp__plugin_github-search_github__list_releases, mcp__plugin_github-search_github__get_latest_release
---

Busca código en GitHub usando el MCP de GitHub.

## Argumentos

`$ARGUMENTS` contiene la query completa tal como la escribió el usuario, por ejemplo:
- `skip_keos_yaml_check repo:Stratio/keos-installer`
- `ClusterClass org:Stratio lang:go`
- `helm_chart_upgrade repo:Stratio/keos-installer`

## Instrucciones

1. Usa `search_code` con la query de `$ARGUMENTS` — los calificadores `repo:`, `org:`, `lang:` son nativos de la API de GitHub.

2. Para cada resultado (máximo 5), usa `get_file_contents` para obtener el contenido del fichero y muestra las líneas relevantes con contexto (±10 líneas alrededor de la coincidencia).

3. Presenta los resultados en este formato:

   ```
   📄 owner/repo — path/to/file.yaml
   🔗 <html_url>

   <fragmento de código con contexto>
   ```

4. Si no hay resultados, sugiere ampliar la búsqueda eliminando filtros.

5. Si hay más de 10 resultados, indica `(mostrando 5 de N)` y sugiere refinar con `repo:` u otros calificadores.
