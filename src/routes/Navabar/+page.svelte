<script>
    import { Navbar, NavBrand, NavLi, NavUl, NavHamburger, Dropdown, DropdownItem, DropdownDivider } from 'flowbite-svelte';
    import { ChevronDownOutline } from 'flowbite-svelte-icons';
    import { page } from '$app/stores';
    $: activeUrl = $page.url.pathname;

    import { Gallery, Button } from 'flowbite-svelte';
  const images = [
    { alt: 'erbology', src: 'https://cdn.pixabay.com/photo/2017/12/17/08/12/girl-3023831_1280.jpg' },
    { alt: 'shoes', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-1.jpg' },
    { alt: 'small bag', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-2.jpg' },
    { alt: 'plants', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-3.jpg' },
    { alt: 'watch', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-4.jpg' },
    { alt: 'shoe', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-5.jpg' },
    { alt: 'cream', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-6.jpg' },
    { alt: 'small bag', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-7.jpg' },
    { alt: 'lamp', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-8.jpg' },
    { alt: 'toiletbag', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-9.jpg' },
    { alt: 'playstation', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-10.jpg' },
    { alt: 'bag', src: 'https://flowbite.s3.amazonaws.com/docs/gallery/square/image-11.jpg' }
  ];



  

</script>
  
<Navbar let:hidden let:toggle>
    <NavBrand href="/">
      <img src="" class="mr-3 h-6 sm:h-9" alt="Flowbite Logo" />
      <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white">Flowbite</span>
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

      <NavLi href="/settings">Sign out</NavLi>
      
</NavUl>
</Navbar>

<div class="flex items-center justify-center py-4 md:py-8 flex-wrap gap-3 mb-3 mx-auto">
    <Button pill size="xl" outline>All categories</Button>
    <Button pill size="xl" color="alternative">Shoes</Button>
    <Button pill size="xl" color="alternative">Bags</Button>
    <Button pill size="xl" color="alternative">Electronics</Button>
    <Button pill size="xl" color="alternative">Gaming</Button>

    
</div>
  
  <Gallery items={images} class="gap-4 grid-cols-2 md:grid-cols-3" />