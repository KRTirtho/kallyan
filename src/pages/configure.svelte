<script lang="ts">
  import {createForm} from "felte";
  import {validator} from "@felte/validator-zod";
  import {z} from "zod";
  
	const {form } = createForm({
    initialValues: {
      email: "",
      password: "",
      host: "",
    },
    validate: validator({
      schema: z.object({
        email: z.string().email(),
        password: z.string(),
        host: z.string(),
      })
    }),
    onSubmit: (values) => {
      // ...
    },
  })
</script>

<h3 class="h3 font-medium mb-4 text-center">Email configurations</h3>

<form class="flex flex-col gap-2 max-w-2xl mx-auto" use:form>
	<div class="flex gap-2 flex-col sm:flex-row">
		<label class="label w-full">
			<span>Email</span>
			<input class="input p-2" type="email" name="email" placeholder="Your email address" />
		</label>
		<label class="label w-full">
			<span>Password</span>
			<input class="input p-2" type="password" name="password" placeholder="Your email password" />
		</label>
	</div>

	<div class="flex gap-2 flex-col sm:flex-row">
		<label class="label w-full">
			<span>User name</span>
			<input class="input p-2" name="host" placeholder="Your full human name" />
		</label>
		<label class="label w-full">
			<span>Host name</span>
			<input class="input p-2" name="host" placeholder="Host name" />
		</label>
	</div>

	<div>
		<button type="submit" class="btn variant-filled-primary float-right">Save & Proceed</button>
	</div>
</form>
