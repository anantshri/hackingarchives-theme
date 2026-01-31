# {{ .Title }}
{{ with .Params.description }}
{{ . }}
{{ end }}
{{ .RawContent }}
{{- if and .File .Params.focus_key -}}
{{- $related_tags := .Params.related_tags -}}
{{- $matching_pages := slice -}}
{{- if $related_tags -}}
{{- range $tag := $related_tags -}}
{{- if isset $.Site.Taxonomies.tag $tag -}}
{{- $matching_pages = $matching_pages | append ($.Site.Taxonomies.tag.Get $tag).Pages -}}
{{- end -}}
{{- end -}}
{{- $matching_pages = sort (uniq $matching_pages) "Date" "desc" -}}
{{- end -}}
{{- if $related_tags }}

## Related Tags
{{ range $related_tags }}- {{ . }}
{{ end -}}
{{- end -}}
{{- if gt (len $matching_pages) 0 }}

## Entries ({{ len $matching_pages }} total)
{{- range $matching_pages.GroupByDate "2006" }}

### {{ .Key }}
{{- range .Pages }}
- [{{ .Title }}]({{ .RelPermalink }}index.md){{ if .Params.hacker }} by {{ range $i, $h := .Params.hacker }}{{ if gt $i 0 }}, {{ end }}{{ $h | humanize | title }}{{ end }}{{ end }}
{{- end -}}
{{- end -}}
{{- end -}}
{{- else -}}
{{- $focusAreaPages := where .Site.Pages "Section" "focus" -}}
{{- $focusAreaPages = where $focusAreaPages ".Params.focus_key" "!=" nil }}

## All Focus Areas
{{ range $focusAreaPages }}
- [{{ .Title }}]({{ .RelPermalink }}index.md){{ if .Params.description }} - {{ .Params.description }}{{ end }}
{{ end -}}
{{- end -}}
