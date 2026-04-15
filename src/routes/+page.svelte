<script>
import WebVM from '$lib/WebVM.svelte';
import * as configObj from '/config_public_alpine';
import { tryPlausible } from '$lib/plausible.js';
function handleProcessCreated(processCount)
{
	// Log the first 5 processes, to get an idea of the level of interaction from the public
	if(processCount <= 5)
	{
		tryPlausible(`Process started: ${processCount}`);
	}
}
</script>

<WebVM configObj={configObj} processCallback={handleProcessCreated} cacheId="xfce_vm_v2">
	<p>Looking for a complete desktop experience? Try the new <a class="underline" href="/alpine.html" target="_blank">Alpine Linux</a> graphical WebVM</p>
</WebVM>
