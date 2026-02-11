{{- $hacker := .Data.Term -}}
{{- /* --- Profile Photo --- */ -}}
{{- $extensions := slice ".jpg" ".png" ".jpeg" ".jfif" ".svg" -}}
{{- $photopath := "" -}}
{{- range $ext := $extensions -}}
  {{- with resources.Get (path.Join "hacker" (printf "%s%s" $hacker $ext)) -}}
    {{- $img := . -}}
    {{- if ne $ext ".svg" -}}
      {{- with try (.Fill "400x400 Center q100") -}}
        {{- if not .Err -}}
          {{- $img = .Value -}}
        {{- end -}}
      {{- end -}}
    {{- end -}}
    {{- $photopath = $img.RelPermalink -}}
    {{- break -}}
  {{- end -}}
{{- end -}}
{{- /* --- Stats Computation (using Scratch.Add for reliable counting) --- */ -}}
{{- $countScratch := newScratch -}}
{{- range .Pages -}}
  {{- $category := .Params.type -}}
  {{- if $category -}}
    {{- $normalizedType := $category | lower | strings.TrimSpace -}}
    {{- if eq $normalizedType "tool demo" -}}
      {{- $normalizedType = "tooldemo" -}}
    {{- end -}}
    {{- $countScratch.Add $normalizedType 1 -}}
  {{- end -}}
{{- end -}}
# {{ .Title }}
{{ if $photopath }}
![Profile photo of {{ .Title }}]({{ $photopath }})
{{ end }}
{{ if .Params.linkedin }}LinkedIn: {{ .Params.linkedin }}
{{ end }}{{ if .Params.twitter }}Twitter: {{ .Params.twitter }}
{{ end }}{{ if .Params.home }}Website: {{ .Params.home }}
{{ end }}{{ if .Params.github }}GitHub: {{ .Params.github }}
{{ end }}
## Stats
{{ with $countScratch.Get "talk" }}
- Talks: {{ . }}
{{ end }}{{ with $countScratch.Get "tooldemo" -}}
- Tool Demos: {{ . }}
{{ end }}{{ with $countScratch.Get "workshop" -}}
- Workshops: {{ . }}
{{ end }}{{ with $countScratch.Get "panel" -}}
- Panels: {{ . }}
{{ end }}{{ with $countScratch.Get "keynote" -}}
- Keynotes: {{ . }}
{{ end }}{{ with $countScratch.Get "book" -}}
- Books: {{ . }}
{{ end }}{{ with $countScratch.Get "award" -}}
- Awards: {{ . }}
{{ end }}{{ with $countScratch.Get "article" -}}
- Articles: {{ . }}
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
