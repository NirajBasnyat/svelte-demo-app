<script>

	let users = {
		firstName: '',
		lastName: '',
		email: '',
	};

	let errors = {
		firstName: '',
		lastName: '',
		email: '',
	};

	let regexEmail = /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/;

	let valid = false;

  let showCard = false;
	const submitForm = (e) => {
		valid = true;

		//validate first name
		if (users.firstName.length <= 1) {
			valid = false;
			errors.firstName = 'First Name is required';
		} else {
			errors.firstName = '';
		}

		//validate last name
		if (users.lastName.length <= 1) {
			valid = false;
			errors.lastName = 'Last Name is required';
		} else {
			errors.lastName = '';
		}

		//validate email
		if (!users.email.match(regexEmail)) {
			valid = false;
			errors.email = 'Enter proper Email';
		} else {
			errors.email = '';
		}

		if (valid) {
      showCard = true;
		}
	};
</script>

<div class="banner mb-5">
	<div class="container pb-2">
		<div class="card mx-3 mt-n5 shadow-lg" style="border-radius:0px; border:none">
			<div class="card-body p-5">
				<h4 class="card-title mb-3 text-dark text-uppercase" style="font-weight:700">Contact Us</h4>

				<form on:submit|preventDefault={submitForm}>
					<div class="row">
						<div class="col">
							<div class="form-floating mb-3">
								<input
									type="text"
									class="form-control"
									id="floatingTextInput1"
									placeholder="John"
									bind:value={users.firstName}
								/>
								<div style="color:red">{errors.firstName}</div>
								<label for="floatingTextInput1">First Name</label>
							</div>
						</div>
						<div class="col">
							<div class="form-floating mb-3">
								<input
									type="text"
									class="form-control"
									id="floatingTextInput2"
									placeholder="Smith"
									bind:value={users.lastName}
								/>
								<div style="color:red">{errors.lastName}</div>
								<label for="floatingTextInput2">Last Name</label>
							</div>
						</div>
					</div>
					<div class="form-floating mb-3">
						<input
							type="email"
							class="form-control"
							id="floatingEmailInput"
							placeholder="name@example.com"
							bind:value={users.email}
						/>
						<div style="color:red">{errors.email}</div>
						<label for="floatingEmailInput">Email address</label>
					</div>

					<div class="text-center">
						<button type="submit" class="btn btn-primary" style="border-radius:0px">Submit</button>
					</div>
				</form>
			</div>
		</div>
	</div>
</div>

{#if (showCard)}
<div class="card">
	<div class="card-body">
		<div>
			<h4>FullName = {users.firstName} {users.lastName}</h4>
			<h4>Email = {users.email}</h4>
		</div>
	</div>
</div>
{/if}