# Wallpapers-Anime

<div id="sitemap">
  <ul id="sitemap-pages">
    <b>Pages:</b>
    <br/>
  </ul>
  <ul id="sitemap-posts">
    <b>Posts:</b>
    <br/>
  </ul>
</div>
<script>
  function loadSitemapPages(json) {
    var sitemap = "<ul>";
    var entries = json.feed.entry || [];
    for (var i = 0; i < entries.length; i++) {
      var entry = entries[i];
      var title = entry.title.$t;
      var link;
      for (var j = 0; j < entry.link.length; j++) {
        if (entry.link[j].rel === 'alternate') {
          link = entry.link[j].href;
          break;
        }
      }
      sitemap += "<li><a href='" + link + "'>" + title + "</a></li>";
    }
    sitemap += "</ul>";
    document.getElementById('sitemap-pages').innerHTML = sitemap;
  }

  function loadSitemapPosts(json) {
    var sitemap = "<ul>";
    var entries = json.feed.entry || [];
    for (var i = 0; i < entries.length; i++) {
      var entry = entries[i];
      var title = entry.title.$t;
      var link;
      for (var j = 0; j < entry.link.length; j++) {
        if (entry.link[j].rel === 'alternate') {
          link = entry.link[j].href;
          break;
        }
      }
      sitemap += "<li><a href='" + link + "'>" + title + "</a></li>";
    }
    sitemap += "</ul>";
    document.getElementById('sitemap-posts').innerHTML = sitemap;
  }
</script>
<script src="https://newyorkmnetwork.blogspot.com/feeds/pages/default?alt=json-in-script&callback=loadSitemapPages"></script>
<script src="https://newyorkmnetwork.blogspot.com/feeds/posts/default?alt=json-in-script&callback=loadSitemapPosts"></script>
