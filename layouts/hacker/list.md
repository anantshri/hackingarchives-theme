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
{{- /* --- Stats Computation --- */ -}}
{{- $categoryCounts := dict -}}
{{- range .Pages -}}
  {{- $category := .Params.type -}}
  {{- if $category -}}
    {{- $categoryCounts = merge $categoryCounts (dict $category (add (index $categoryCounts $category | default 0) 1)) -}}
  {{- end -}}
{{- end -}}
{{- $normalizedCounts := dict -}}
{{- range $category, $count := $categoryCounts -}}
  {{- $normalizedType := $category | lower | strings.TrimSpace -}}
  {{- if eq $normalizedType "tool demo" -}}
    {{- $normalizedType = "tooldemo" -}}
  {{- end -}}
  {{- if not (isset $normalizedCounts $normalizedType) -}}
    {{- $normalizedCounts = merge $normalizedCounts (dict $normalizedType $count) -}}
  {{- else -}}
    {{- $existingCount := index $normalizedCounts $normalizedType -}}
    {{- $normalizedCounts = merge $normalizedCounts (dict $normalizedType (add $existingCount $count)) -}}
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
{{ with index $normalizedCounts "talk" }}
- Talks: {{ . }}
{{ end }}{{ with index $normalizedCounts "tooldemo" -}}
- Tool Demos: {{ . }}
{{ end }}{{ with index $normalizedCounts "workshop" -}}
- Workshops: {{ . }}
{{ end }}{{ with index $normalizedCounts "panel" -}}
- Panels: {{ . }}
{{ end }}{{ with index $normalizedCounts "keynote" -}}
- Keynotes: {{ . }}
{{ end }}{{ with index $normalizedCounts "book" -}}
- Books: {{ . }}
{{ end }}{{ with index $normalizedCounts "award" -}}
- Awards: {{ . }}
{{ end }}{{ with index $normalizedCounts "article" -}}
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
