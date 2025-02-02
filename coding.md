---
layout: article
---

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <script>
        async function fetchRepoData(element) {
            const username = element.getAttribute('data-username');
            const repo = element.getAttribute('data-repo');

            if (!username || !repo) {
                element.textContent = 'Missing username or repository name.';
                return;
            }

            const url = `https://api.github.com/repos/${username}/${repo}`;

            try {
                const response = await fetch(url);
                if (!response.ok) {
                    throw new Error(`Error: ${response.statusText}`);
                }

                const data = await response.json();
                const creationDate = new Date(data.created_at);

                element.textContent = `Repo created on: ${creationDate.toLocaleDateString()}`;
            } catch (error) {
                console.log(error);
                element.textContent = `Failed to fetch data: ${error.message}`;
            }
        }

        window.onload = () => {
            document.querySelectorAll('p[data-username][data-repo]').forEach(fetchRepoData);
        };
    </script>
</head>

<body>
<div class="coding-item">
    <a href="https://github.com/hereismari/tensorflow-maml"><img src="https://github.com/hereismari/tensorflow-maml/raw/master/imgs/maml_vs_nn.png" style="float:left;"></a>
    <h4>MAML in TF 2.0</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="tensorflow-maml">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=tensorflow-maml&type=star&count=true" frameborder="0" scrolling="0" title="GitHub" class="github-link"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=tensorflow-maml&type=fork&count=true" frameborder="0" scrolling="0" title="GitHub" class="github-link"></iframe>
    </div>
    <div class="description">
        <p>Reproduction of the <a href='https://arxiv.org/abs/1703.03400'>MAML paper</a> using TensorFlow 2.0.</p>
    </div>
</div>

<div class="coding-item">
    <a href="https://github.com/hereismari/playing-games-with-tfjs"><img src="https://github.com/hereismari/playing-games-with-tfjs/raw/master/demo/demo_tetris1.gif" style="float:left;"></a>
    <h4>Playing a game using TF JS</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="playing-games-with-tfjs">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=playing-games-with-tfjs&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=playing-games-with-tfjs&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>I’ve built a demo using TensorFlow JS to play different games just using a camera!</p>
    </div>
</div>

<div class="coding-item">
    <a href="https://github.com/hereismari/tf-eager-text-generation"><img src="https://github.com/hereismari/tf-eager-text-generation/raw/master/utils/colors.png" style="float:left;"></a>
    <h4>Text generation with tf.eager</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="tf-eager-text-generation">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=tf-eager-text-generation&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=tf-eager-text-generation&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>Modified version of <a href='https://www.tensorflow.org/tutorials/sequences/text_generation'>TensorFlow tutorial about text generation</a>
        using TensorFlow Eager. Including fun examples.</p>
    </div>
</div>

 <div class="coding-item">
    <a href="https://github.com/hereismari/mnist-android-tensorflow"><img src="img/mnist-android.gif" style="float:left;"></a>
    <h4>MNIST on Android</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="mnist-android-tensorflow">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=mnist-android-tensorflow&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=mnist-android-tensorflow&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>A MNIST model ready to run on Android, including instructions about how to do it on your own.
           <a href="https://www.youtube.com/watch?v=kFWKdLOxykE&t=67s">This work was featured in a video from Siraj Raval</a>!!! The video has > 150k views!</p>
    </div>
</div>

<div class="coding-item">
    <a href="https://github.com/hereismari/easy21"><img src="https://github.com/hereismari/easy21/raw/master/imgs/sarsa.gif" style="float:left;"></a>
    <h4>Easy 21 Assignment</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="easy21">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=easy21&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=easy21&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>An introduction to RL by solving the Easy21 assignment from the RL class by David Silver.</p>
    </div>
</div>

<div class="coding-item">
    <a href="https://github.com/hereismari/spotify-flask"><img src="img/spotify-flask.png" style="float:left;"></a>
    <h4>Spotify-Flask</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="spotify-flask">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=spotify-flask&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=spotify-flask&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>Request data from Spotify API using Flask. It also includes pre-built templates.</p>
    </div>
</div>

<div class="coding-item">
    <a href="https://github.com/hereismari/DeepLearning"><img src="img/deep.png" style="float:left;"></a>
    <h4>Learning Deep Learning</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="DeepLearning">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=DeepLearning&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=DeepLearning&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>This repository keeps track of my path towards getting started with Deep Learning (mainly with TensorFlow).</p>
    </div>
</div>

<div class="coding-item">
    <a href="https://github.com/hereismari/UVaCPTracker"><img src="img/uvacptracker.gif" style="float:left;"></a>
    <h4>UVaCPTracker</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="UVaCPTracker">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=UVaCPTracker&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=UVaCPTracker&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>UVaCPTracker is a Chrome extension that makes it easier to keep track of how many problems in Competitive Programming a user has already solved. <a href="https://chrome.google.com/webstore/detail/uvacptracker/ankphgpmnicdkehhmnklhlodkfkecjbh" target="_blank">Download here!</a></p>
    </div>
</div>

<div class="coding-item">
    <a href="https://github.com/hereismari/spotifyoutube"><img src="img/spotifyoutube.gif" style="float:left;"></a>
    <h4>SpotifYoutube</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="spotifyoutube">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=spotifyoutube&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=spotifyoutube&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>A Chrome extension that connects YouTube with Spotify through a button. It allows users to go from YouTube music videos to songs, albums, or bands in Spotify. <a href="https://chrome.google.com/webstore/detail/spotifyoutube/ankphgpmnicdkehhmnklhlodkfkecjbh" target="_blank">Download here!</a></p>
    </div>
</div>

<div class="coding-item">
    <a href="https://github.com/hereismari/a2oj-as-csv"><img src="img/a2ojascsv.png" style="float:left;"></a>
    <h4>A2OJ as CSV</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="a2oj-as-csv">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=a2oj-as-csv&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=a2oj-as-csv&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>Python script that takes an <a href="https://a2oj.com/">a2oj</a> standing and returns a CSV with the submissions information.</p>
    </div>
</div>

<div class="coding-item">
    <a href="https://github.com/hereismari/Programming"><img src="img/cp.jpg" style="float:left;"></a>
    <h4>Algorithms for Competitive Programming</h4>
    <div class="github-info">
        <p data-username="hereismari" data-repo="Programming">Loading...</p>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=Programming&type=star&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
        <iframe src="https://ghbtns.com/github-btn.html?user=hereismari&repo=Programming&type=fork&count=true" frameborder="0" scrolling="0" class="github-link" title="GitHub"></iframe>
    </div>
    <div class="description">
        <p>Python script that takes an <a href="https://a2oj.com/">a2oj</a> standing and returns a CSV with the submissions information.</p>
    </div>
</div>


</body>
