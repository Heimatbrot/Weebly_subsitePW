# HTML_sitepw

HTML_sitepw is a html script which you can add to your website, to make it password locked. The password is being saved for 12h in the users cache. After 12h (where the user didn't visit this website) the cache is being cleared and you have to re-enter the password.


# how to set up
1. add following code to your website: 
```ruby
<!DOCTYPE html>
<html>
<body>

  var skeypass1secret = "PASSWORD HERE";
  
  <pre id="file-content"></pre>
  <script>
    const url = "https://api.github.com/repos/{username}/{repo}/contents/{filepath}";
    const username = "your-github-username";
    const repo = "your-github-repo";
    const filepath = "path/to/your/file.html";

    fetch(url.replace("{username}", username).replace("{repo}", repo).replace("{filepath}", filepath))
      .then(response => response.json())
      .then(data => {
        const decodedContent = atob(data.content); // decode base64-encoded content
        document.getElementById("file-content").textContent = decodedContent;
      })
      .catch(error => console.error(error));
  </script>
</body>
</html>
```
