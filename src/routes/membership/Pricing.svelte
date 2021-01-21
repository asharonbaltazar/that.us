<script>
  import { useMachine } from 'xstate-svelte';

  import { debug } from '../../config';
  import { cart } from '../../utilities/cart';

  import Layout from './components/_Layout.svelte';
  import LogoCloud from './components/_LogoCloud.svelte';

  import Hero from './components/pricing/_Hero.svelte';
  import Quote from './components/pricing/_Quote.svelte';
  import FAQs from './components/pricing/_FAQs.svelte';
  import NotReady from './components/pricing/_NotReady.svelte';
  import PricingCore from './components/pricing/_PricingCore.svelte';

  const { send } = useMachine($cart, {
    devTools: debug.xstate,
  });
</script>

<Layout>
  <Hero />
  <Quote />
  <PricingCore />
  <LogoCloud />
  <FAQs />
  <NotReady />
</Layout>
