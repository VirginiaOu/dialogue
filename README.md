# dialogue
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>评论区</title>
</head>
<body>
    <h1>评论区</h1>
    <form id="comment-form">
        <label for="username">用户名：</label>
        <input type="text" id="username" required>
        <br>
        <label for="comment">评论：</label>
        <textarea id="comment" required></textarea>
        <br>
        <button type="submit">提交评论</button>
    </form>
    <div id="comments"></div>
    <script>
        document.getElementById('comment-form').addEventListener('submit', function(event) {
            event.preventDefault();
            var username = document.getElementById('username').value;
            var comment = document.getElementById('comment').value;
            var commentsDiv = document.getElementById('comments');
            var newComment = document.createElement('div');
            newComment.innerHTML = '<strong>' + username + '：</strong>' + comment;
            commentsDiv.appendChild(newComment);
            document.getElementById('username').value = '';
            document.getElementById('comment').value = '';
        });
    </script>
</body>
</html>
