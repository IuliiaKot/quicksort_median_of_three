# QuicksortMedianOfThree

## Description

Quicksort is an efficient sorting algorithm, serving as a systematic method for placing the elements of an array in order.
Quicksort is a divide and conquer algorithm. Quicksort first divides a large array into two smaller sub-arrays: the low elements and the high elements. Quicksort can then recursively sort the sub-arrays.

The steps are:

    1.Pick an element, called a pivot, from the array.
    2.Reorder the array so that all elements with values less than the pivot come before the pivot, while all elements with values greater than the pivot come after it (equal values can go either way). After this partitioning, the pivot is in its final position. This is called the partition operation.
    3.Recursively apply the above steps to the sub-array of elements with smaller values and separately to the sub-array of elements with greater values.

There are some ways how you can choose a pivot element: the first element, the last element or random element.

Bur Sedgewick suggested some optimizations:
    1. Pivot element is median-of-three.
    2.To make sure at most O(log n) space is used, recurse first into the smaller side of the partition, then use a tail call to recurse into the other.
    3.Use insertion sort, which has a smaller constant factor and is thus faster on small arrays, for invocations on small arrays (i.e. where the length is less than a threshold k determined experimentally). This can be implemented by simply stopping the recursion when less than k elements are left, leaving the entire array k-sorted: each element will be at most k positions away from its final position. Then, a single insertion sort pass[13]:117 finishes the sort in O(kn) time. A separate insertion sort of each small segment as they are identified adds the overhead of starting and stopping many small sorts, but avoids wasting effort comparing keys across the many segment boundaries, where keys will be in order due to the workings of the quicksort process.


## Installation

Add this line to your application's Gemfile:

```ruby
gem 'quicksort_median_of_three'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install quicksort_median_of_three

## Usage

TODO: Write usage instructions here

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release` to create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

1. Fork it ( https://github.com/[my-github-username]/quicksort_median_of_three/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
