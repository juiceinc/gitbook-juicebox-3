# Hashes

Many computer things are called "hash," but in a Juicebox context the term usually refers to a **Hashr `UserHash`**.

Hashr is a mechanism in Juicebox responsible for storing snapshots of the state of the user interface of a [Stack](). On GitHub: [juiceinc/fruition/hashr](https://github.com/juiceinc/fruition/tree/develop/hashr)

This helps us to improve the platform usability, as a user can leave and return to a Stack at a later time, even using a different browser, to find it just how they left it.

Hashr serializes the UI state into JSON format, compresses it, and stores it in DynamoDB.

Hashr uses the UI state to calculate an ID. In practice, if two users generate the same state, Hashr will calculate the same ID, so only one copy of the state needs to be stored.

Hashr's `UserHash` holds the ID referencing the stored state, along with references to the user that generated it and the stack it applies to.

## Deleting hashes

Sometimes, a change made to an App may invalidate the UI state created using older versions. We do not currently have a mechanism to version hashes, or to migrate old hashes to work with newer apps, or to make Apps ignore old versions. Unfortunately, a mismatch between hash and App version can cause the App to misbehave.

So, on these occasions, we may need to clear the now-invalid hashes. This can be accomplished in the Juicebox Admin:

* Navigate to Stacks -&gt; Apps
* Select \(by checking\) the apps whose hashes should be deleted.
* Select "Delete all hashes for selected apps"
* Click "Go"

## Other things called "hash"

In computer science, a _hash_ is the output of a [hash function](https://en.wikipedia.org/wiki/Hash_function). To _hash_ some data is to apply a hash function to it.

Hash functions are used to build _hash tables_, which are used to implement key/value mapping structures with fast lookup speeds \(also known as _associative arrays_ or _dictionaries_.\)

Confusingly, Perl's hash-table-backed mapping structures are themselves referred to simply as "[hashes](http://perl101.org/hashes.html)." Likewise, Ruby's mapping structure is also called a "[Hash](https://docs.ruby-lang.org/en/trunk/Hash.html)."

SHA-1 is a hash function used in cryptography, and also by the version control system `git` to compute its commit IDs. As such, you may sometimes hear commit IDs referred to as _commit hashes_ or _git hashes_.

The octothorpe character \(\#\) is sometimes called "hash."

Perhaps appropriately, "hash" can also mean "a confused mess."

