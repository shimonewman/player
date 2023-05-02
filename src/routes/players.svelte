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

    let projectId, videoId, mode, output;

    projectId = $page.url.searchParams.get('projectId');
    videoId   = $page.url.searchParams.get('videoId');
    output    = $page.url.searchParams.get('output');
    mode      = $page.url.searchParams.get('mode');

    function loadPlayers() {
        ;
    }

</script>
<style>
    .frm{
       border:0px;
     }
</style>
<head>
    <meta charset="utf-8">
    <link rel="icon" href="favicon.png">
    <title>Appwrite test players</title>
</head>

    <div style="display: flex;flex-wrap: wrap">
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
        <div><iframe src="/player?projectId={projectId}&videoId={videoId}&mode={mode}&output={output}" class="frm"></iframe></div>
    </div>
    <br>
<div style="margin: auto;width: 50%;padding: 10px;">
    <div style="display:inline-block">
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
        <button type="button" on:click={loadPlayers} style="background-color:#FFC0CB;border-radius: 6px;">Load</button>
    </form>
    </div>
</div>