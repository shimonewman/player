<script lang="ts">

    import {page} from "$app/stores";
    import { onMount } from 'svelte';

    const contentType = [];
    contentType["hls"] = "application/x-mpegurl";
    contentType["dash"] = "application/dash+xml";

    const fileName = [];
    fileName["hls"] = "master.m3u8";
    fileName["dash"] = "master.mpd";

    const url = [];
    url["local"] = "http://127.0.0.1";
    url["remote"] = "https://vod.appwrite.org";

    const projectId = $page.url.searchParams.get('projectId');
    const videoId   = $page.url.searchParams.get('videoId');
    const output    = $page.url.searchParams.get('output');
    const mode      = $page.url.searchParams.get('mode');

    onMount(async () => {
        setTimeout(() => {
            let player = videojs('video-player');
            player.stop();
        }, 1000);
    });

</script>
<video id="video-player"  class="video-js vjs-default-skin " controls autoplay  style="width:240px;height:135px">
    <source src={`${url[mode]}/v1/videos/${videoId}/outputs/${output}/${fileName[output]}?project=${projectId}`} type={contentType[output]} />
</video>



