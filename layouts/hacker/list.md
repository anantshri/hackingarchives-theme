# {{ .Title }}

{{ if .Params.linkedin }}LinkedIn: {{ .Params.linkedin }}
{{ end }}{{ if .Params.twitter }}Twitter: {{ .Params.twitter }}
{{ end }}{{ if .Params.home }}Website: {{ .Params.home }}
{{ end }}{{ if .Params.github }}GitHub: {{ .Params.github }}
{{ end }}
{{- if .Pages }}

## Talks & Presentations
{{- range .Pages.GroupByDate "2006" }}

### {{ .Key }}
{{- range .Pages }}
- [{{ .Title }}]({{ .RelPermalink }}index.md){{ if .Params.conference }} @ {{ .Params.conference | humanize | title }}{{ end }}
{{- end }}
{{- end }}
{{- end }}
