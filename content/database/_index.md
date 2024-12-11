+++
title = "Database"
sort_by = "date"
template = "section.html"
+++

{{ range .Pages.ByDate.Reverse }}
  <article>
    <h2><a href="{{ .RelPermalink }}">{{ .Title }}</a></h2>
    <time>{{ .Date.Format "2006-01-02" }}</time>
  </article>
{{ end }}