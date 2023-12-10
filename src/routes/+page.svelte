<script>
    import "carbon-components-svelte/css/white.css";
    import {
      Header,
      HeaderNav,
      HeaderNavItem,
      HeaderNavMenu,
      SkipToContent,
      Content,
      Grid,
      Row,
      Column,
    } from "carbon-components-svelte";
    import { DataTable, Link } from "carbon-components-svelte";
    import Launch from "carbon-icons-svelte/lib/Launch.svelte";
  
    let isSideNavOpen = false;
  </script>
  
  <Header company="Barcode" platformName="Print" bind:isSideNavOpen>
    <svelte:fragment slot="skip-to-content">
      <SkipToContent />
    </svelte:fragment>
    <HeaderNav>
      <!--HeaderNavItem href="/" text="Link 1" />
      <HeaderNavItem href="/" text="Link 2" />
      <HeaderNavItem href="/" text="Link 3" />
      <HeaderNavMenu text="Menu">
        <HeaderNavItem href="/" text="Link 1" />
        <HeaderNavItem href="/" text="Link 2" />
        <HeaderNavItem href="/" text="Link 3" />
      </HeaderNavMenu-->
    </HeaderNav>
  </Header>
  
  <Content>
    <Grid>
      <Row>
        <Column>
          

              
              <DataTable
                headers={[
                  { key: "name", value: "Name" },
                  { key: "diz", value: "Description" },
                  { key: "bcode", value: "Barcode" },
                  { key: "price", value: "Price" },
                ]}
                rows={[
                  {
                    id: "1",
                    name: "ผงซุบฟ้าไทย",
                    diz: "40 กรัม",
                    bcode: "30001",
                    price: "14.00",
                  },
                  {
                    id: "2",
                    name: "ผงซุบฟ้าไทย",
                    diz: "โหล 12 ชิ้น",
                    bcode: "30002",
                    price: "140.00",
                  },
                  {
                    id: "3",
                    name: "ซีอิ๊วขาวสูตร 1 ",
                    diz: "เด็กสมบูรณ์",
                    bcode: "30003",
                    price: "35.00",
                  },
                ]}
              >

                <svelte:fragment slot="cell" let:row let:cell>
                  {#if cell.key === "name" }
                    <Link
                      icon={Launch}
                      href="https://en.wikipedia.org/wiki/Round-robin_DNS"
                      target="_blank">{cell.value}</Link
                    >
                  {:else}
                    {cell.value}
                  {/if}
                </svelte:fragment>
              </DataTable>
              
            



        </Column>
      </Row>
    </Grid>
  </Content>
  