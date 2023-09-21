<script>
    import { Navbar, NavBrand, NavLi, NavUl, NavHamburger, Dropdown, DropdownItem, DropdownDivider } from 'flowbite-svelte';
    import { ChevronDownOutline } from 'flowbite-svelte-icons';
    import { page } from '$app/stores';
    $: activeUrl = $page.url.pathname;

    import { Gallery, Button } from 'flowbite-svelte';
  const images = [
    { alt: 'erbology', src: 'https://cdn.pixabay.com/photo/2017/12/17/08/12/girl-3023831_1280.jpg' },
    { alt: 'shoes', src: 'https://cdn.pixabay.com/photo/2017/12/17/08/12/girl-3023831_1280.jpg' },
    { alt: 'small bag', src: 'https://cdn.pixabay.com/photo/2017/12/17/08/12/girl-3023831_1280.jpg' },
    { alt: 'plants', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-3.jpg' },
    { alt: 'watch', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-4.jpg' },
    { alt: 'shoe', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-5.jpg' },
    { alt: 'cream', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-6.jpg' },
    { alt: 'small bag', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-7.jpg' },
    { alt: 'lamp', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-8.jpg' },
    { alt: 'toiletbag', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-9.jpg' },
    { alt: 'playstation', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-10.jpg' },
    { alt: 'bag', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-11.jpg' },
  ];


</script>
  
<Navbar let:hidden let:toggle>
    <NavBrand href="/">
      <!-- <img src="" class="mr-3 h-6 sm:h-9" alt="Flowbite Logo" /> -->
      <span class="self-center whitespace-nowrap text-xl font-bold text-red-500">Photo gallery</span>
    </NavBrand>
    <NavHamburger on:click={toggle} />
 <NavUl {hidden} {activeUrl}>
      <NavLi href="/">Home</NavLi>
      <NavLi class="cursor-pointer">
        
        University<ChevronDownOutline class="w-3 h-3 ml-2 text-primary-800 dark:text-white inline" />
      </NavLi>
      <Dropdown class="w-44 z-20">
        <DropdownItem href="/">Limkokwing</DropdownItem>
        <DropdownItem href="/docs/components/navbar">IPAM</DropdownItem>
        <DropdownItem href="/">FBC</DropdownItem>
        <DropdownDivider />
        <DropdownItem href="/"> Njala</DropdownItem>
        <DropdownItem href="/"> Unimak</DropdownItem>
        <DropdownItem href="/"> EBK</DropdownItem>
      </Dropdown>

    <NavLi class="cursor-pointer">
        
        Year<ChevronDownOutline class="w-3 h-3 ml-2 text-primary-800 dark:text-white inline" />
    </NavLi>
      <Dropdown class="w-44 z-20">
        <DropdownItem href="/">class of 2019</DropdownItem>
        <DropdownItem href="/docs/components/navbar">class of 2020</DropdownItem>
        <DropdownItem href="/">class of 2021</DropdownItem>
        <DropdownDivider />
        <DropdownItem href="/"> class of 2022</DropdownItem>
        <DropdownItem href="/"> class of 2023</DropdownItem>
        <DropdownItem href="/"> class of 2024</DropdownItem>
      </Dropdown>


      <NavLi href="/Landingpage">Sign out</NavLi>
      
</NavUl>
</Navbar>

<div class="flex items-center justify-center py-4 md:py-8 flex-wrap gap-3 mb-3 mx-auto">
    <Button pill size="xl" outline>Limkokwing 2022</Button>
    <Button pill size="xl" color="alternative">2021</Button>
    <Button pill size="xl" color="alternative">2022</Button>
    <Button pill size="xl" color="alternative">2023</Button>
    <!-- <Button pill size="xl" color="alternative">2024</Button> -->

    <form id="upload-form" enctype="multipart/form-data" class="flex">
        <!-- Image Upload -->
        <div class="mb-4 ">
            <label for="image" class="block font-semibold mb-2 ml-4" >Choose an image:</label>
            <input type="file" id="image" name="image" accept="image/*" class="border border-red-300 p-2 w-50">
        </div>

        <!-- Caption Input -->
        <div class="mb-4 w-1/4 h-5 ml-5 mt-3">
          <label for="caption" class="block font-semibold mb-2" >Caption:</label>
          <input type="text">
          <!-- <textarea id="caption" name="caption" class="border border-gray-300 p-2 w-50 h-20 resize-yes"></textarea> -->
      </div>
        

        <!-- Submit Button -->
        <div class="ml-5">
            <button type="submit" class="bg-red-500 hover:bg-red-600 text-white font-semibold py-2 px-4 rounded-full mt-10  ml-5">Upload image</button>
        </div>
        
        
    </form>
    <!-- <Button pill size="xl" color="alternative" bg-green-100>upload</Button> -->
    

    
</div>


  <Gallery items={images} class="gap-4 grid-cols-2 md:grid-cols-3" />