#!/usr/bin/env python3

import os, sys, configparser

CONFIG_FILE = os.path.expanduser('~/.pharo')

def print_choices_for(typed, choices):
    results = list(filter(lambda choice: choice.startswith(typed), choices))
    if len(results) == 1:
        print(results[0])
    else:
        complete_partially(typed, results)
        print('\n' + ' '.join(results))

def get_all_items(section):
    config = configparser.RawConfigParser()
    config.read(CONFIG_FILE)
    return map(lambda item: item[0], config.items(section))

def complete_partially(typed, results):
    cmd = os.path.commonprefix(results)
    if len(cmd) > 1 and not cmd == typed: print(cmd)

choices = {
  'pharo'  : ['add', 'remove', 'list', 'launch', 'help'],
  'add'    : ['image', 'vm'],
  'launch' : get_all_items('vms'),
  'remove' : ['image', 'vm'],
  'image'  : get_all_items('images'),
  'vm'     : get_all_items('vms')
}

try: print_choices_for(sys.argv[2], choices[sys.argv[3]])
except KeyError:
    if sys.argv[3] in get_all_items('vms'):
        print_choices_for(sys.argv[2], get_all_items('images'))
