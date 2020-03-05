# Django Lifecycle Hooks

[![Package version](https://badge.fury.io/py/django-lifecycle.svg)](https://pypi.python.org/pypi/django-lifecycle)
[![Python versions](https://img.shields.io/pypi/status/django-lifecycle.svg)](https://img.shields.io/pypi/status/django-lifecycle.svg/)

This project provides a `@hook` decorator as well as a base model and mixin to add lifecycle hooks to your Django models. Django's built-in approach to offering lifecycle hooks is [Signals](https://docs.djangoproject.com/en/dev/topics/signals/). However, my team often finds that Signals introduce unnesseary indirection and are at odds with Django's "fat models" approach.

## Fork Update
**Removed LifeCycleModel** in order to not get an error when used with Django 3.0

**Django Lifecycle Hooks** supports Python 3.5, 3.6, and 3.7, Django 2.0.x, 2.1.x, 2.2.x. 3


**Documentation**: <a href="https://rsinger86.github.io/django-lifecycle/" target="_blank">https://rsinger86.github.io/django-lifecycle</a>

**Source Code**: <a href="https://github.com/rsinger86/django-lifecycle/" target="_blank">https://github.com/rsinger86/django-lifecycle</a>

---

# Changelog

## 0.7.1 (January 2020)
* Fixes bug in `utils._get_field_names` that could cause recursion bug in some cases.

## 0.7.0 (December 2019)
* Adds `changes_to` condition - thanks @samitnuk! Also some typo fixes in docs.

## 0.6.1 (November 2019)
* Remove variable type annotation for Python 3.5 compatability.

## 0.6.0 (October 2019)
* Adds `when_any` hook parameter to watch multiple fields for state changes

## 0.5.0 (September 2019)
* Adds `was_not` condition
* Allow watching changes to FK model field values, not just FK references

## 0.4.2 (July 2019)
* Fixes missing README.md issue that broke install.

## 0.4.1 (June 2019)
* Fixes [urlman](https://github.com/andrewgodwin/urlman)-compatability.

## 0.4.0 (May 2019)
* Fixes `initial_value(field_name)` behavior - should return value even if no change. Thanks @adamJLev!

## 0.3.2 (February 2019)
* Fixes bug preventing hooks from firing for custom PKs. Thanks @atugushev!

## 0.3.1 (August 2018)
* Fixes m2m field bug, in which accessing auto-generated reverse field in `before_create` causes exception b/c PK does not exist yet. Thanks @garyd203!

## 0.3.0 (April 2018)
* Resets model's comparison state for hook conditions after `save` called.

## 0.2.4 (April 2018)
* Fixed support for adding multiple `@hook` decorators to same method.

## 0.2.3 (April 2018)
* Removes residual mixin methods from earlier implementation.

## 0.2.2 (April 2018)
* Save method now accepts `skip_hooks`, an optional boolean keyword argument that controls whether hooked methods are called.

## 0.2.1 (April 2018)
* Fixed bug in `_potentially_hooked_methods` that caused unwanted side effects by accessing model instance methods decorated with `@cache_property` or `@property`. 

## 0.2.0 (April 2018)
* Added Django 1.8 support. Thanks @jtiai!
* Tox testing added for Python 3.4, 3.5, 3.6 and Django 1.8, 1.11 and 2.0. Thanks @jtiai!

# Testing

Tests are found in a simplified Django project in the ```/tests``` folder. Install the project requirements and do ```./manage.py test``` to run them.

# License

See [License](LICENSE.md).
