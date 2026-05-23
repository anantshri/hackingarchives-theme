# {{ .Title }}
{{ if .Params.hacker }}
By: {{ range $index, $author := .Params.hacker }}{{ if gt $index 0 }}, {{ end }}{{ . | humanize | title }}{{ end }}
{{ end }}
{{ if .Params.conference }}Conference: {{ .Params.conference | humanize | title }}{{ end }}
{{ if .Date }}Year: {{ .Date.Year }}{{ end }}
{{ if .Params.date }}Date: {{ .Date.Format "2006-01-02" }}{{ end }}

{{ if .Params.tag }}Tags: {{ range $index, $tag := .Params.tag }}{{ if gt $index 0 }}, {{ end }}{{ $tag }}{{ end }}{{ end }}

{{ if or .Params.presentation .Params.whitepaper .Params.video .Params.conf_link .Params.Source }}
## Resources
{{ if .Params.conf_link }}- Conference Link: {{ .Params.conf_link }}
{{ end }}{{ if .Params.presentation }}- Presentation: {{ .Params.presentation }}
{{ end }}{{ if .Params.whitepaper }}- Whitepaper: {{ .Params.whitepaper }}
{{ end }}{{ if .Params.video }}- Video: {{ .Params.video }}
{{ end }}{{ if .Params.Source }}- Source Code: {{ .Params.Source }}
{{ end }}{{ end }}

{{ .RawContent }}
