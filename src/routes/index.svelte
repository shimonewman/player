<script lang="ts">

    import {page} from "$app/stores";

    const contentType = [];
    contentType["hls"] = "application/x-mpegurl";
    contentType["dash"] = "application/dash+xml";

    const fileName = [];
    fileName["hls"] = "master.m3u8";
    fileName["dash"] = "master.mpd";

    const url = [];
    url["local"] = "http://127.0.0.1";
    url["remote"] = "https:/video.appwrite.org";

    let projectId = $page.url.searchParams.get('projectId');
    let videoId   = $page.url.searchParams.get('videoId');
    let mode, output;
    let src = 'Countdown video@2x_1_v2.mp4';
    let type = 'video/mp4';

    function loadAsset() {

        // videojs.Hls.xhr.beforeRequest = (options: any) => {
        // 	if (!options.headers) {
        // 		options.headers = {};
        // 	}
        // 	options.headers['x-appwrite-project'] = projectId;
        // 	return options;
        //};

        let player =  videojs('video-player');
        src = `${url[mode]}/v1/videos/${videoId}/outputs/${output}/${fileName[output]}?project=${projectId}`;
        type = contentType[output]
        player.src({
            src: src,
            type: type
        });
        player.play();
    }

</script>
<style>
    .container {
        margin-top:50px;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
</style>
<head>
    <meta charset="utf-8">
    <link rel="icon" href="favicon.png">
    <title>Appwrite test player</title>
</head>
<div class="container">
    <div>
        <input type="text" bind:value={src} style="width:900px;margin-bottom: 20px"/>
    </div>
    <div  style="width:960px;height:540px">
        <video id="video-player"  class="video-js vjs-default-skin " controls autoplay style="width:960px;height:540px">
            <source src={src} type="{type}"/>
        </video>
    </div>
    <div style="margin-top: 20px">
        <form id="playerForm" name="playerForm">
            <select id=mode bind:value={mode}>
                <option value="local">Local</option>
                <option value="remote">Remote</option>
            </select>
            <select id="output" bind:value={output}>
                <option value="hls">HLS</option>
                <option value="dash">DASH</option>
            </select>
            <input id="projectId" type="text" bind:value={projectId} style="width:200px" placeholder="projectId"/>
            <input id="videoId" type="text" bind:value={videoId} style="width:200px" placeholder="videoId"/>
            <button type="button" on:click={loadAsset} style="background-color:#FFC0CB;border-radius: 6px;">Load</button>
        </form>
    </div>
</div>


