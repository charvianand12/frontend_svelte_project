<script>
	export let open = true
	
	let subMenuOpen = null;
	let contentSectionOpen = false; // Initialize the content section's state

let menuItems = [
	{	
		label: "Collections",
		icon: "/src/images/download.png",
		submenuItems: [
			{ label: "Submenu Item 1" },
			{ label: "Submenu Item 2" },
			// Add more submenu items
		]
	},
	{	
		label: "APIs",
		icon: "/src/images/download.png",
		submenuItems: [
			{ label: "Submenu Item 2" },
			{ label: "Submenu Item 3" },
			// Add more submenu items
		]
	},
	{	
		label: "Environment",
		icon: "/src/images/download.png",
		submenuItems: [
			{ label: "Submenu Item 4" },
			{ label: "Submenu Item 6" },
			// Add more submenu items
		]
	},
	{	
		label: "Servers",
		icon: "/src/images/download.png",
		submenuItems: [
			{ label: "Submenu Item 7" },
			{ label: "Submenu Item 8" },
			// Add more submenu items
		]
	},
	{	
		label: "Notifications",
		icon: "/src/images/download.png",
		submenuItems: [
			{ label: "Submenu Item 1" },
			{ label: "Submenu Item 2" },
			// Add more submenu items
		]
	},{	
		label: "History",
		icon: "/src/images/download.png",
		submenuItems: [
			{ label: "Submenu Item 1" },
			{ label: "Submenu Item 2" },
			// Add more submenu items
		]
	},
	// Add more menu items
];
function toggleContentSection() {
        contentSectionOpen = !contentSectionOpen;
    }

function toggleSubMenu(index) {
	if (subMenuOpen === index) {
		subMenuOpen = null;
	} else {
		subMenuOpen = index;
	}
}
</script>









<aside class="absolute w-full h-full bg-gray-200 border-r-2 shadow-lg left-0 top-0 h-18 w-16" class:open>
	<nav> <br>
		<div class="workspace">
		<b>WORKSPACE</b></div>
		<ul class="nav" role="tablist">
            {#each menuItems as item, index}
                <li class="nav-item" role="presentation">
					<!-- <img alt="collection" src="/src/images/download.png"> -->
                    <a on:click={() => toggleSubMenu(index)} class="nav-link" role="tab">
                        {#if item.icon}
                            <img src={item.icon} alt="" class="menu-icon" />
                        {/if}
						{item.label}
                    </a>
					<span></span>
							<div class="sub-menu-container" class:open={subMenuOpen === index}>
                    <!-- {#if subMenuOpen === index} -->
							<div class="collapsible-section">
                        <ul class="sub-menu" style="left: 100%; top: 0;">
                            {#each item.submenuItems as subitem}
                                <li>{subitem.label}</li>
                            {/each}
                        </ul>
                </li>
            {/each}
        
	</nav>
</aside>


<section class="content-section margin-left: 0px">
	<div class="colored-rectangle">
			{#each menuItems as item, index}
					<div class="foldable-option">
							<a on:click={() => toggleSubMenu(index)} class="option-link">
								
							</a>
							<ul class="sub-menu" class:open={subMenuOpen === index}>
									{#each item.submenuItems as subitem}
											<li>{subitem.label}</li>
									{/each}
							</ul>
					</div>
			{/each}
	</div>
</section>

<style>
	img {
        max-width: 60%; 
        height: 40px;
		background-color: "grey";
		
    }
	aside {
		float:left; 
		position: fixed;
		/* left: -500px; */
		height: 10000px;
		width: 150px;
		padding: 20px;
		border: solid;
		background-color: whitesmoke;
		order: 2;
		top: 2;
		transition: left 0.3s ease-in-out;
		/* transition: left 0.3s ease-in-out */
	}

	aside {
		float:left; 
		position: fixed;
		/* left: -500px; */
		height: 10000px;
		width: 150px;
		padding: 20px;
		border: none;
		background-color:whitesmoke;
		order: 2;
		top: 3;
		transition: left 0.3s ease-in-out;
		/* transition: left 0.3s ease-in-out */
	}
	
	
	.nav-item {
        margin-bottom: 38px; 
		margin-top: 38px;
		position: relative;
		color: #3B71CA;/* Add space between menu items */
    }

	.open {
		left: 0;
		margin-top: 59px;

	}
	.menu-icon {
        display: block;
        width: 20px; /* Adjust the icon/image size */
        height: 20px;
        margin-bottom: 5px;
		margin-left: 50px; /* Add spacing between icon and label */
    }
		.sub-menu-container {
        position: absolute;
        top: 0;
        left: 100%; /* Position the submenu to the right */
        display: none;
    }

    .sub-menu-container.open {
        display: block;
    }

		/* .collapsible-section {
        display: {subMenuOpen === index ? 'block' : 'none'};
        max-height: {subMenuOpen === index ? '1000px' : '0'};
        overflow: hidden;
        transition: max-height 0.3s ease-in-out;
    } */
	/* .sub-menu {
        position: absolute;
        top: 0;
        left: 50%; /* Position the submenu to the right */
        /* display: none; Hide the submenu by default */
    /* } */

		.content-section {
        float: left;
        position: absolute;
        left: 216px; /* Adjust this value to create space for the sidebar */
        width: calc(10% - 216px); /* Adjust the width accordingly */
        padding: 20px;
        order: 3;
        top: 0;
    }

    .colored-rectangle {
        float: left;
        position: fixed;
        left: 150px; /* Adjust this value to create space for the sidebar */
        height: 100%; /* Adjust the height to cover the full height */
        width: 90px; /* Adjust the width for the colored rectangle */
        padding: 20px;
        background-color: whitesmoke;
        order: 2;
        top: 0;
        transition: left 0.3s ease-in-out;
        margin-top: 59px; /* Adjust this value to align with the sidebar */
    }

    .foldable-option {
        margin-bottom: 20px;
    }

    .option-link {
        display: block;
        cursor: pointer;
    }

    .option-icon {
        max-width: 10%;
        height: 20px;
        background-color: grey;
    }

    .sub-menu {
        display: none;
		color: black;
    }

    .sub-menu.open {
        display: block;
    }
	.workspace{
		color: blue;
	}
	.sub-menu-container{
		color: black;
	}
</style>