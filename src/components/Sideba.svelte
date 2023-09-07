<script>  
import {
  Collapse,
  Ripple,
  initTE,
} from "tw-elements";

initTE({ Collapse, Ripple });
</script>


<div class="collapse">
    <button
    class="inline-block rounded bg-primary px-6 pb-2 pt-2.5 text-xs font-medium uppercase leading-normal text-white shadow-[0_4px_9px_-4px_#3b71ca] transition duration-150 ease-in-out hover:bg-primary-600 hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:bg-primary-600 focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] focus:outline-none focus:ring-0 active:bg-primary-700 active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.3),0_4px_18px_0_rgba(59,113,202,0.2)] dark:shadow-[0_4px_9px_-4px_rgba(59,113,202,0.5)] dark:hover:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:focus:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)] dark:active:shadow-[0_8px_9px_-4px_rgba(59,113,202,0.2),0_4px_18px_0_rgba(59,113,202,0.1)]"
    type="button"
    data-te-collapse-init
    data-te-target="#collapseWidthExample"
    data-te-ripple-init
    data-te-ripple-color="light"
    aria-expanded="false"
    aria-controls="collapseWidthExample">
    Toggle width collapse
    </button>
    <div class="sub-menu">
        <div
        class="!visible hidden rounded-lg shadow-lg"
        data-te-collapse-item
        data-te-collapse-horizontal
        id="collapseWidthExample">
            <div
                class="block w-[300px] max-w-sm rounded-lg bg-white p-6 shadow-[0_2px_15px_-3px_rgba(0,0,0,0.07),0_10px_20px_-2px_rgba(0,0,0,0.04)] dark:bg-neutral-700 dark:text-neutral-50">
                This is some placeholder content for a horizontal collapse. It's
                hidden by default and shown when triggered.
            </div>
        </div>
    </div>
</div>

<style lang="postcss">
.sub-menu:hover {background-color: #ddd;}

.collapse:hover .sub-menu {display: block;}

/* .dropdown:hover .dropbtn {background-color: grey;} */
</style>
