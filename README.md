# react-convertkit-form

ConvertKit's email capture in React:

```tsx
export const ConvertKitForm = () => (
  <form
    method="post"
    action={`https://app.convertkit.com/forms/${FORM_ID}/subscriptions`}
    className="seva-form formkit-form"
    data-sv-form={FORM_ID}
    data-options={JSON.stringify(dataOptions)}
  >
    <div data-style="clean">
      <ul className="formkit-alert formkit-alert-error" data-element="errors" data-group="alert" />
      <div data-element="fields" data-stacked="false" className="seva-fields formkit-fields">
        <div className="formkit-field">
          <input
            type="email"
            name="email_address"
            className="formkit-input"
            aria-label="Email Address"
            placeholder="Email Address"
            required
          />
          <div className="formkit-spinner" />
          <button>
            <span className="">Subscribe</span>
          </button>
        </div>
      </div>
    </div>
  </form>
);

const dataOptions = {
  settings: {
    after_subscribe: {
      action: 'message',
      success_message: 'Success! Now check your email to confirm your subscription.',
      redirect_url: ''
    },
    analytics: {
      google: null,
      fathom: null,
      facebook: null,
      segment: null,
      pinterest: null,
      sparkloop: null,
      googletagmanager: null
    },
    modal: {
      trigger: 'timer',
      scroll_percentage: null,
      timer: 5,
      devices: 'all',
      show_once_every: 15
    },
    powered_by: {
      show: true,
      url: 'https://convertkit.com/features/forms?utm_campaign=poweredby&amp;utm_content=form&amp;utm_medium=referral&amp;utm_source=dynamic'
    },
    recaptcha: { enabled: false },
    return_visitor: { action: 'show', custom_content: '' },
    slide_in: {
      display_in: 'bottom_right',
      trigger: 'timer',
      scroll_percentage: null,
      timer: 5,
      devices: 'all',
      show_once_every: 15
    },
    sticky_bar: {
      display_in: 'top',
      trigger: 'timer',
      scroll_percentage: null,
      timer: 5,
      devices: 'all',
      show_once_every: 15
    }
  },
  version: '5'
};
```

And don't forget to add the script tag somewhere in your DOM.

```html
<script src="https://f.convertkit.com/ckjs/ck.5.js" />
```
