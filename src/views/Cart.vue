<template>
<div class="container">
  <table id="cart" class="table table-hover table-condensed">
    <thead>
      <tr>
							<th style="width:50%">Product</th>
							<th style="width:10%">Price</th>
							<th style="width:8%">Quantity</th>
							<th style="width:22%" class="text-center">Subtotal</th>
							<th style="width:10%"></th>
						</tr>
					</thead>
					<tbody>
						<CartItem v-for="item in cart" :key="item.id" :item="item" />
					</tbody>
					<tfoot>
						<tr class="visible-xs">
							<td class="text-center"><strong>Total 1.99</strong></td>
						</tr>
						<tr>
							<td><a href="#" class="btn btn-warning"><i class="fa fa-angle-left"></i> Continue Shopping</a></td>
							<td colspan="2" class="hidden-xs"></td>
							<td class="hidden-xs text-center"><strong>Total $1.99</strong></td>
							<td><a href="#" class="btn btn-success btn-block">Checkout <i class="fa fa-angle-right"></i></a></td>
						</tr>
					</tfoot>
				</table>
</div>
</template>

<script>
import CartItem from "@/components/CartItem.vue";

export default {
  name: 'Cart',
  data () {
    return {
      quantity: '',
      subtotal: ''
    }
  },
  components: {
	  CartItem
  },
  methods: {
  },
  computed: {
    cart () {
      console.log(this.$store.state.cart)
      return this.$store.state.cart
    }
  }
}
</script>

<style>
form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center
}
</style>
