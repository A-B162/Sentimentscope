<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Social Media Sentiment Analyzer</title>
  <style>
    body { font-family: Arial, sans-serif; text-align: center; padding: 50px; }
    button { padding: 15px 30px; margin: 10px; font-size: 16px; cursor: pointer; }
  </style>
</head>
<body>
  <h1>Social Media Sentiment Analyzer</h1>
  <p>Share your Facebook or Instagram posts to get instant sentiment analysis!</p>

  <button id="fb-share">Share from Facebook</button>
  <button id="ig-share">Share from Instagram</button>

  <script>
    // Replace with your actual App IDs
    const FB_APP_ID = "813342444588613";
    const IG_APP_ID = "738197419219413";

    // Your redirect URL (where your backend handles OAuth callback)
    const REDIRECT_URI = "https://github.com/A-B162/Sentimentscope.com/oauth/callback";

    // Facebook OAuth
    document.getElementById("fb-share").onclick = function() {
      const scope = "user_posts";
      const oauthUrl = `https://www.facebook.com/v20.0/dialog/oauth?client_id=${FB_APP_ID}&redirect_uri=${REDIRECT_URI}?platform=facebook&scope=${scope}&response_type=code`;
      window.location.href = oauthUrl;
    };

    // Instagram OAuth
    document.getElementById("ig-share").onclick = function() {
      const scope = "user_profile,user_media";
      const oauthUrl = `https://api.instagram.com/oauth/authorize?client_id=${IG_APP_ID}&redirect_uri=${REDIRECT_URI}?platform=instagram&scope=${scope}&response_type=code`;
      window.location.href = oauthUrl;
    };
  </script>
</body>
</html>


