# {{ .Title | humanize | title }}

{{ .RawContent }}

{{- if .Pages }}
{{- range .Pages.GroupByDate "2006" }}

## {{ .Key }}
{{- range .Pages }}
- [{{ .Title }}]({{ .RelPermalink }}index.md)
{{- end }}
{{- end }}
{{- end }}
