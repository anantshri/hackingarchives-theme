# {{ .Title | humanize | title }}

{{ .RawContent }}

{{- range .Pages }}
- [{{ .Title }}]({{ .RelPermalink }}index.md) ({{ len .Pages }} entries)
{{- end }}
